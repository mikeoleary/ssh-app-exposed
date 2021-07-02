# File Server App
simple demo app to expose port 22 from K8s pod

This simple demo assumes you already have F5 CIS set up and functioning correctly. 

You will want to edit the file called ```config-map.yaml``` so that the IP address(es) match what you would like configured.

After that, run
````
git clone https://github.com/mikeoleary/ssh-app-exposed.git
kubectl apply -f ns.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f config-map.yaml
````

Now you should see an application exposed on your BIG-IP:

![Image](images/image.PNG)

Thanks!
