# Welcome to Oracle Open World 2017 - EventHub Hands On Lab

## Introduction

EventHub Cloud Service is Oracle's Open Source Kafka Streaming Data service. In this lab, you will be seting up an EventHub Cluster in Oracle Cloud and stream data through it. This lab is devided into 3 sections

**Section#1**: Setting up an EventHub Cluster (Apache Zookeeper, Kafka Brokers), Configure and Create a Kafka Topic

**Section#2**: SSH into the EventHub Cluster and use Kafka built in tools to produce and consume data

**Section#3** (Advanced): Deploy a Microservice app (NodeJS) in Application Container Cloud Service

##Prerequisites
- Internet access on your laptop
- Oracle Cloud Account user name, password, data center infomation ( this will be provided in the lab)
- Ability to SSH to the Oracle Cloud from your Terminal (Mac) or Putty (Windows)


### Section #1: Setting up an EventHub Cluster (Apache Zookeeper, Kafka Brokers), Configure and Create a Kafka Topic

### Step 1: Login to the Oracle Cloud

Log into Oracle Cloud : https://cloud.oracle.com/en_US/sign-in

**Select _Traditional Cloud Account_ and Data Center to be us2 **


![](images/cloudlogin.png)

** - Select EventHub - Dedicated Cloud Service**
![](images/dashboard.png)


** - Go to the Service console**
![](images/serviceconsole.png)

### Step 2: Create your EventHub Cluster

![](images/createCluster.png)

** Download a pre-made public and private ssh key from the GitHub repo. This will be needed for the configuraiton in the next page.

![](images/configureClusterandCreate.png)

![](images/clustercreated.png)

** This should take a couple minutes **

### Step 3: Create a Topic in your cluster


# Upload to Oracle Application Container Cloud

## Producer application

- Access the **Applications** list view

![](images/accs_create_app_1.jpg)

- Click **Create Application** and select **Node**.

![](images/accs_create_app_node.jpg)

- In the **Create Application** section, enter a name for your application, replace the **Notification Email** address with your own (or leave it blank) and click **Choose File** next to **Archive**
- On the File Upload dialog box, select the `TwitterProducerApp.zip` file and click **Open**
- Click **Choose File** next to **Deployment Configuration**
- On the File Upload dialog box, select the `deployment.json` file click **Open**
- Finally, click **Create** to start the application deployment

![](images/accs_create_app_2.jpg)

Once the application is deployed, you should see it in the **Applications** menu

![](images/accs-deployed-app.jpg)


Producer application starts pushing tweets in real time to Oracle Event Hub Cloud once it gets deployed

## Consumer application

- In the Applications list view, click **Create Application** and select **Java EE**.

![](images/accs_create_app_javaee.jpg)

- In the **Create Application** section, enter a name for your application, replace the Notification Email address with your own (or leave it blank) and click **Choose File** next to **Archive**
- On the File Upload dialog box, select the `accs-kafka-tweet-consumer.war` file and click **Open**
- Click **Choose File** next to **Deployment Configuration**
- On the File Upload dialog box, select the `deployment.json` file click **Open**
- Finally, click **Create** to start the application deployment

Once the application is deployed, you should see it in the **Applications** menu

# Access the application

## Consumer application

To start seeing the tweet stream, open the consumer application URL in your browser - e.g. `https://TwitterConsumerApp-test.apaas.us2.oraclecloud.com`

## Change tweet filter criteria

If you want to change the hashtag for the tweets you want to see, just use the following URL `<ACCS_PRODUCER_APP_URL>/hashtag/<your_hashtags>` e.g. `https://TwitterProducerApp-test.apaas.us2.oraclecloud.com/hastag/hurricane,java,kafka`
