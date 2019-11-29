# How to ... Java !

## Install let's encrypt certificates for java/win

```
curl https://letsencrypt.org/certs/letsencryptauthorityx1.der --output letsencryptauthorityx1.der
curl https://letsencrypt.org/certs/letsencryptauthorityx2.der --output letsencryptauthorityx2.der
curl https://letsencrypt.org/certs/lets-encrypt-x1-cross-signed.der --output lets-encrypt-x1-cross-signed.der
curl https://letsencrypt.org/certs/lets-encrypt-x2-cross-signed.der --output lets-encrypt-x2-cross-signed.der
curl https://letsencrypt.org/certs/lets-encrypt-x3-cross-signed.der --output lets-encrypt-x3-cross-signed.der
curl https://letsencrypt.org/certs/lets-encrypt-x4-cross-signed.der --output lets-encrypt-x4-cross-signed.der

keytool -trustcacerts -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -storepass changeit -noprompt -importcert -alias isrgrootx1 -file letsencryptauthorityx1.der
keytool -trustcacerts -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -storepass changeit -noprompt -importcert -alias isrgrootx2 -file letsencryptauthorityx2.der
keytool -trustcacerts -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -storepass changeit -noprompt -importcert -alias letsencryptauthorityx1 -file lets-encrypt-x1-cross-signed.der
keytool -trustcacerts -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -storepass changeit -noprompt -importcert -alias letsencryptauthorityx2 -file lets-encrypt-x2-cross-signed.der
keytool -trustcacerts -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -storepass changeit -noprompt -importcert -alias letsencryptauthorityx3 -file lets-encrypt-x3-cross-signed.der
keytool -trustcacerts -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -storepass changeit -noprompt -importcert -alias letsencryptauthorityx4 -file lets-encrypt-x4-cross-signed.der
```
