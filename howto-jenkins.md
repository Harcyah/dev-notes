# How to ... Jenkins !

## View stored ssh keys

Using jenkins console at `http://host/script`:

```groovy
import jenkins.model.*
import com.cloudbees.plugins.credentials.*
import com.cloudbees.plugins.credentials.common.*
import com.cloudbees.plugins.credentials.domains.*
import com.cloudbees.jenkins.plugins.sshcredentials.impl.*
import hudson.plugins.sshslaves.*

Jenkins jenkins = Jenkins.getInstance()

def domain = Domain.global()

def store = jenkins.getExtensionList('com.cloudbees.plugins.credentials.SystemCredentialsProvider')[0].getStore()

def creds = store.getCredentials(domain)
def cred = creds[0];

def pkey = cred.getPrivateKey();
```
