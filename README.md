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

**update && upgrade && reboot the system as user root**

```ts
        - apt update -y
        - apt upgrade 
        - reboot 
```
**install docker CE**

```ts
        - apt-get install docker.io -y   // install docker with package manager apt-get
        - systemctl start docker  // start the service ddocker 
        - systemctl enable docker // Configure Docker to start on boot with systemd
        - systemctl status docker //check the status of the service docker 
```
**download openshift from repository github** 

```ts
        - wget https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz 
              // get the fichier from repo to local 
        - tar -xvzf openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
              // extract the file 
        - cd openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit // change directory to the file 
        - cp oc kubectl /usr/local/bin/ //copy oc,kubectl to directory bin 
        - oc version //to verified is all correct
        - nano /etc/docker/daemon.json //create the file ,to authorize the use of the registry Insecure Docker
                     - {  
                            "insecure-registries" : [ "172.30.0.0/16" ]     
                       }
                    // add it to file daemon.json 
        - systemctl restart docker // restart the Docker service to implement the modifications
        - 



```
**Start the OpenShift cluster** 

```ts
        - oc cluster up --public-hostname=your-server-ip // run the cluster by specifying $your_address_ip 
 
        - oc login -u system:admin //connect to your cluster as administrator
        - oc project default // for expose the project at a port 
        - oc status // to check the status of your project 
        - oc describe // for more details
        - oc cluster down // Shutting down the cluster 

```

**Create a project on Openshift** 

```ts
        - oc login  // entre your user/pwd
        - oc new-project dev --display-name="Project - Dev" --description="My Projec" // create a new project specifyie 
        - oc project default // for expose the project at a port 
        - oc status // to check the status of your project 
        - oc describe // for more details
        - oc cluster down // Shutting down the cluster 

```

**Deployment an application on Openshift** 

```ts
        - oc login  // entre your user/pwd
        - oc project my-project // change to project my-project
        - oc tag --source=docker openshift/app:v2 app:latest // tag image from docker hub  
        - oc new-app app // deploy the image with tag llatest 
        - oc get svc // information about your service (svc)
        - oc describe svc app // more details about the service 
        - oc get pods  // status of your pods  
        - oc expose service/app  // expose your deployment to external access
        - oc get route // to get the URL 

```




**To cleanup the deployment** 

```ts
        - oc delete all -l app=app // delete the pods,replicationcontroller,service,route,... everthings that create to the project.

```

[resume pdf](./CR_TP2_IPS3_Ou-sbaa_Hafid.pdf) 


