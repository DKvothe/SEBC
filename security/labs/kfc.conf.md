# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = DKVOTHE.COM
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac

[realms]
  DKVOTHE.COM = {
  kdc = ip-172-31-26-69.us-east-2.compute.internal
  admin_server = ip-172-31-26-69.us-east-2.compute.internal
 }

[domain_realm]
   .dkvothe.com = DKVOTHE.COM
   dkvothe.com = DKVOTHE.COM

[root@ip-172-31-26-69 ec2-user]# cat /var/kerberos/krb5kdc/kdc.conf
[kdcdefaults]
 max_life = 1d
 max_renewable_life = 7d
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
 DKVOTHE.COM = {
  #master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes256-cts:normal aes128-cts:normal des3-hmac-sha1:normal arcfour-hmac:normal camellia256-cts:normal camellia128-cts:normal des-hmac-sha1:normal des-cbc-md5:normal des-cbc-crc:normal
 }
