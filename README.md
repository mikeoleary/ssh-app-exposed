# File Server App
Simple demo app to expose port 22 from K8s pod

This simple demo assumes you already have F5 CIS set up and functioning correctly to process Config Maps. 

* You will want to edit the file called ```config-map.yaml``` so that the IP address(es) match what you would like configured.
* You will also want to edit ```deployment.yaml``` to point to your own image. The example image here is ubuntu, which by default does not have SSH enabled. Therefore if you change nothing your pool member will show in the GUI as red (health monitor will fail because SSH is not running in pod).

After that, run
````
git clone https://github.com/mikeoleary/ssh-app-exposed.git
cd ssh-app-exposed
kubectl apply -f ns.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f config-map.yaml
````

Now you should see an application exposed on your BIG-IP:

![Image](images/virtual-servers.PNG)

With a pool member:

![Image2](images/pool-members.PNG)

Thanks!
