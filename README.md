# -Implement-an-PaaS-private-cloud-solution-with-OpenShift.
                   ![openshift](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/OpenShift-LogoType.svg/langfr-330px-OpenShift-LogoType.svg.png)
----------------------------------------------------------------------

**create virtual machine VM**


```go
         minimum requirements 

           -Ubuntu
           -16 Go RAM
           -100 Go hard disk 

           
```           

**update && upgrade && reboot the system from the user root**

```js
        - apt update -y
        - apt upgrade 
        - reboot 
```
**install docker CE**

```js
        - apt-get install docker.io -y   // install docker with package manager apt-get
        - systemctl start docker  // start the service ddocker 
        - systemctl enable docker // Configure Docker to start on boot with systemd
        - systemctl status docker //check the status of the service docker 
```
**download openshift from repository github** 

```js
        - wget https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz 
              // get the fichier from repo to local 
        - tar -xvzf openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
              // extract the file 
        - cd openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit // change directory to the file 
        - cp oc kubectl /usr/local/bin/ //copy oc,kubectl to directory bin 
        - oc version //verfier version to check is all okay

```
