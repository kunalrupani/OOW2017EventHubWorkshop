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