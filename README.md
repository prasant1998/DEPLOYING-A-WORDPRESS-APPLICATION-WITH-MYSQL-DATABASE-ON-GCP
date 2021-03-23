I have to create multiple projects namely developer and production and then add VPC network for both the projects then create a link between both the VPC networks using VPC Peering then create a Kubernetes Cluster in deveproject and launch any web application with the Load balancer then create a SQL server in the prodproject and create a database and atlast connect the SQL database to the web application launched in the Kubernetes cluster.

![1](https://user-images.githubusercontent.com/67523396/112204319-878b2600-8c39-11eb-950b-69e29532e998.jpeg)


STEP 1

I have created multiple projects named devproject and prodproject.As we create multiple projects to give flexibility to the client users and company to seprate there billling account and give seprate space to their workers to work on convinently ,etc.

![2](https://user-images.githubusercontent.com/67523396/112204321-8823bc80-8c39-11eb-92a2-e08fcac3254e.png)
![3](https://user-images.githubusercontent.com/67523396/112204324-8823bc80-8c39-11eb-894f-b61e2fb87171.png)


STEP 2

Linked both the projects with billing account.We have to link our projects with billing account to take the services served by google ,To every services there are many API(Application programming interface ) to give us services.

![4](https://user-images.githubusercontent.com/67523396/112204326-88bc5300-8c39-11eb-9c1f-0edbaf528c39.png)


STEP 3

Created VPC network for both the projects .As we created Vpc network ,firewall will not allow other ip to enter our OS ..So we add one more firewall rule with 0.0.0.0/0 ip and port=80 to allow every ip to enter our OS and just take the services given by port no -80 in our OS ,so by default port no 80 gives the service of webserver but we can change it too by a small change in configuration file of the software which is allowing us to host our web server.

![5](https://user-images.githubusercontent.com/67523396/112204327-8954e980-8c39-11eb-8969-f5f5eec0dee4.png)
![6](https://user-images.githubusercontent.com/67523396/112204330-89ed8000-8c39-11eb-843a-ae1ead9b8d78.png)
![7](https://user-images.githubusercontent.com/67523396/112204333-8a861680-8c39-11eb-8820-02a34c6a5eb9.png)


STEP 4

Created a link between both the VPC networks using *VPC Peering*.Google provide us with two ip one public ip and 2nd private ip .As we know about public ip , private ip is something in which google provide us to use there network channel which is spread all over the world ,As it transfers our data safely and very fast .So an example to understand it more better , A Company development team is working on the data centre of region asia-southeast1(Jurong West,Singapore) in zone “b”and production team is working on the data centre of us-east1(Moncks Corner, South Carolina, USA) in zone “c” .So if they want to transfer there data which is very beneficial to the company they send it through private network provided by Google.

![8](https://user-images.githubusercontent.com/67523396/112204337-8b1ead00-8c39-11eb-85d7-dacea41a3e71.png)
![9](https://user-images.githubusercontent.com/67523396/112204294-80fcae80-8c39-11eb-9068-078540387565.png)



STEP 5

Created a Kubernetes Cluster in devproject by adding three nodes in diffrent zones and launched wordpress on one of the deployment pod.Why deployment pod ?? it is because if by mistake a pod in which wordpress is launched is deleted then it launches a new pod with the same setting everything same ,then i made 5 more replicas of the pod to balance the load on the server …To balance the load on the server i had added Load Balancer service too and added load balancer on top of those 5 replicas .Here kubernetes works as a manager to manage everything.We have to configure Network setting and allow everyone to access port no 80 .

![10](https://user-images.githubusercontent.com/67523396/112204300-82c67200-8c39-11eb-935f-d4a2377b60bc.png)
![11](https://user-images.githubusercontent.com/67523396/112204302-82c67200-8c39-11eb-901d-53ec69c4fd49.png)
![12](https://user-images.githubusercontent.com/67523396/112204303-835f0880-8c39-11eb-87d2-1f7b11e25f1c.png)
![13](https://user-images.githubusercontent.com/67523396/112204305-83f79f00-8c39-11eb-9eee-5ef62b02fd3b.png)



STEP 6

Created a SQL server in the prodproject as sql service provides us with three more storage facilities MySQL ,PostgreSQL SQL Server …I moved further with MySQL service as i had to make a database so then i created an instance with password and then configured networking and created a database.

![14](https://user-images.githubusercontent.com/67523396/112204307-84903580-8c39-11eb-901a-56e8d9497e10.png)
![15](https://user-images.githubusercontent.com/67523396/112204309-8528cc00-8c39-11eb-8ec6-898b29ae6b3f.png)
![16](https://user-images.githubusercontent.com/67523396/112204311-85c16280-8c39-11eb-8e98-8972e2e6743e.png)



STEP 7

Connected the SQL database to the web application launched in the Kubernetes cluster.By ip of Load Balancer to the pods ,I opened wordpress and then added sql database name, then user name ie, root, then password of sql and then ip of sql instance .After the next page shows up we are connected …


![17](https://user-images.githubusercontent.com/67523396/112204313-8659f900-8c39-11eb-9147-6e4674883d79.png)
![18](https://user-images.githubusercontent.com/67523396/112204314-86f28f80-8c39-11eb-9a65-2a5073514365.png)
![19](https://user-images.githubusercontent.com/67523396/112204316-86f28f80-8c39-11eb-8af4-bb43a4bf3e0f.png)



THANK YOU
