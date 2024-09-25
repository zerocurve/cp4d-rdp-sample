#Cloudpak for Data Remote Dataplane Application

##Background
Cloud Pak for Data platform introduced Remote Data Planes in 5.0. This new framework is now available in Cloud Pak for Data version 5.0. Remote Data Planes augments the Cloud Pak for Data platform to extend beyond the traditional OpenShift cluster to span across multiple clusters both on-premises and in the cloud as one instance for a hybrid experience. This new framework removes the restriction of running workloads in just one location, where users can choose to run the workloads closer to the data source in a different location all under one instance. Users can now create a workload definition on the Cloud Pak for Data control plane and deploy them to a remote data plane. This innovation brings the processing capabilities to the data for data gravity, and at the same time meets data regulations and compliance for data sovereignty, which reduces the need to transfer data

Remote data plane allows users to bring their own workloads on the platform. The Cloud Pak for Data users now can package their own application as a set of yaml file and put them into a deployable package then deploy through a remote dataplane API. This capability allows users to unlock the third party application on cloud pak for data platform, and get addtional value to distribute the workoad on multiple clusters.

<img width="1115" alt="image" src="https://github.com/user-attachments/assets/5710f06b-0476-4293-8cbc-17d69872ba83">

#This innovation brings several values for the Cloud Pak for Data platform:
- One instance: consolidates user workload on the single cp4d instance
- Optimize resource management: run on-premises and scale out to the cloud
- Centralize monitoring: Cloudpak for data administrator now can centralize monitor the third party application through monitor page
- Soft quota: Cloudpak for data administrator can put quota on thirdparty app, and enforce the quota in the future
- Integrated User management: Cloudpak for data platform as central platform for user to launch their applications.

#how to use the example
##pre-requisite setup
The setup and configuration first starts with creating the physical locations on the remote OpenShift cluster and then defining the remote data plane using the physical location.
Physical Location
The setup of the physical locations is handled using command line tools that creates and registers the physical location. The first step is to install the Cloud Pak for Data management agent at the physical location in a namespace. This is lightweight agent that uses a smaller footprint than a complete Cloud Pak for Data instance. The second step is to ra egister the physical location to establish mutual trust between physical location and the Cloud Pak for Data control plane. For more details and instructions please refer Setting up the remote physical location for IBM Cloud Pak for Data in the documentation.
Data Plane
After the remote physical locations are setup, the Cloud Pak for Data platform administrator can proceed to create the data planes using the Cloud Pak for Data control plane console. One or more remote physical locations can be assigned to a data plane. In the Configurations and Settings page the administrator can view the physical locations registered and manage data planes in the respective tabs.

##package the application
Cloudpak for data user need download the repo code and package the application through following command:

tar -cvzf "ray-app.tar.gz" -C app . 

