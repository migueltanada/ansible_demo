# If LDAP is mapped correctly but initial users are unable to authenticate
## Change passwords of initial users.
- create changepass.ldif
```
cat <<EOF > sample.ldif
dn: cn=jenkins,ou=people,dc=ldap,dc=alexforbes,dc=net
changetype: modify
replace: userPassword
userPassword: jenkins

dn: cn=adop,ou=people,dc=ldap,dc=alexforbes,dc=net
changetype: modify
replace: userPassword
userPassword: adop

dn: cn=nexus,ou=people,dc=ldap,dc=alexforbes,dc=net
changetype: modify
replace: userPassword
userPassword: nexus
EOF
```
- Copy ldif File to Container.\
``oc cp sample.ldif <ldap pod name>:/``
- Enter Ldap Pod.\
``oc rsh <pod>``
- Execute LDIF.\
``ldapadd -x -D "cn=admin,dc=ldap,dc=alexforbes,dc=net" -w <SLAPD_PASSWORD> -H ldap:// -f sample.ldif  ``



