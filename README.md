Create a cluster and deploy a workload
Learn how to:
1.	Create a Kubernetes cluster, which provides compute, storage, networking, and other services for applications, similar to a virtual data center.
2.	Deploy a sample app to the cluster. Apps and their associated services that are running in Kubernetes are called workloads.
3.	View a live demo of the sample workload in your browser.
Estimated time, including time waiting for cluster creation:
 
15 minutes
Difficulty:
Choose a Google Cloud project for your cluster
A Google Cloud project is a collection of resources that you use to build and manage your applications on Google Cloud.
1.	Create a new project to ensure that you have the permissions you need, or select an existing project in which you have the relevant permissions.


Upgrade your Free Trial
If you've used all of your credits or reached the end of your Free Trial, you must activate a full account to continue using Google Cloud. Activate to keep any remaining credits to spend during your trial and to avoid a disruption in service.
2.	The necessary APIs are enabled:
o	Kubernetes Engine API
To create a GKE cluster in the project you chose, click Next.
Create a cluster in GKE Autopilot mode
In Autopilot mode, Google manages your cluster configuration, including scaling, security, and other preconfigured settings. Clusters in Autopilot mode are optimized to run most production workloads and provision compute resources based on your Kubernetes manifests.
1.	Go to the GKE Create an Autopilot cluster page.
Go to Create an Autopilot cluster
2.	Under Cluster basics, do the following:
a.	In the Name field, enter the following name:
hello-world-cluster

b.	Keep the default values for the rest of the settings and click Create to start creating the cluster.
3.	When you're redirected to the Kubernetes clusters page, you can watch the progress of your cluster as it is being configured, deployed, and verified.
4.	Wait until you see a check mark next to the hello-world-cluster page title.
To deploy a sample app to the GKE cluster, click Next.
Deploy a sample app to your cluster
Deploy a sample "hello world" web app provided by Google and stored as a container in Artifact Registry.
1.	In the Google Cloud console, go to the GKE Workloads page.
Go to Workloads
2.	Click Deploy.
3.	In Deployment name, enter the following name:
hello-world-app

4.	In Kubernetes Cluster, select hello-world-cluster.
5.	Click Next: Container details
6.	Leave Existing container image selected, and in Image path enter the following path:
us-docker.pkg.dev/google-samples/containers/gke/hello-app:1.0

This simple "hello world" app is packaged into a single container, but larger apps typically consist of several related containers that can be deployed together and run as a single workload.
7.	Click Next: Expose (optional)
8.	In the Expose section, create a load balancing Kubernetes Service to direct external requests to your app:
a.	Select Expose deployment as a new service.
b.	Leave Port 1 set to 80.
c.	In Target port 1, enter 8080.
d.	Click Deploy.
GKE automatically assigns an available external IP address to the Service.
This Service is considered to be part of the hello-world-app workload.
9.	For Autopilot clusters, you might see an error message, such as Does not have minimum availability. This occurs because Autopilot deletes and then re-creates the nodes. Wait a few minutes, then click refreshRefresh to update the page.
10.	Wait until the deployment completes and you see the Deployment details page.
To view a live demo of the hello-world-app workload, click Next.
View a live demo in your browser
1.	If you aren't already on the Deployment details page for hello-world-app:
a.	In the Google Cloud console, go to the GKE Workloads page.
Go to Workloads
b.	In the Name column, click the name of the workload you deployed, hello-world-app.
2.	In the Endpoints column, click the IP address, which is publicly available.
GKE opens a new browser tab and sends a request to your app. Dismiss any secure-site warnings, and you should see Hello, world! in the new browser tab.
If Endpoints is empty, your organization might have a policy that prevents external access.
You have successfully created a GKE cluster in Autopilot mode and deployed a sample workload.
 
To learn about the next steps, click Next. 
View and learn about the following workload settings and resources that you deployed to a cluster:
•	The Deployment specification, which defines the desired state for your workload
•	Pods, which are computing units that replicate as needed to maintain your desired state
•	Services, which provide a stable endpoint for your Pods


