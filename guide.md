# Datastreams
A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web and Mobile SDKs. Datastream is a configuration defines how data is collected, processed, and sent to various destinations.

## Setting Up a Datastream in Adobe Experience Platform

### Steps:

1. **Navigate to Data Collection:** Go to the **Data Collection** section from the main menu.

2. **Create a New Datastream:** Click on **Datastreams** in the left-hand menu and select **Create a Datastream**.

                                                   **Create Datastream**

4. **Configure Datastream Settings:** Provide a descriptive name for your datastream. You can also add the description.

5. **Select Mapping Schema:** Choose the mapping schema you want to use with this specific datastream. You can create a datastream without specifying the schema as well. 

6. **Geolocation And Network Lookup:** Tick off geolocation and network information that you want to collect with your datastream.

7. **Save:** Double check the settings and click on save.

                                                   **Save**
   
## Event Forwarding
Lets learn what event forwarding is before we learn how to configure a service in datastream. 

Event forwarding in Adobe Experience Platform allows you to send collected event data to a destination for server-side processing. Event forwarding decreases web page and app weight by using Adobe Experience Platform Edge Network to execute tasks normally done on the client. Implemented in a similar manner to tags, event forwarding rules can transform and send data to new destinations, but instead of sending this data from a client application like a web browser, it is sent from Adobe’s servers.

## Create Event Forwarding Property

### Steps:

1. **Select Event Forwarding:** Under event forwarding in your left hand panel, click on event forwarding.
2. **Create the property:**Click on **New Property** and give it an appropriate name and click on **Save**

                                                   **Create Property**

## Adding Event Forwarding Service

### Steps:

1. **Access Your Datastream:** Once you have created a datastream, locate and open it in Adobe Experience Platform.

2. **Add a Service:** Click on **Add a Service** within your datastream.

                                                   **Add Service**

4. **Select Service Type:** From the dropdown list, select **Event Forwarding** as the service type.

                                                   **Service Type**

5. **Map to Event Forwarding Property:** Choose your desired event forwarding property from the dropdown list to map it accordingly.

6. **Select Environment:**
   - Specify the environment you wish to use for this service.

7. **Save Configuration:**
   - Click **Save** to finalize and apply your service configuration.

After you have created the datastreams and the property and configured the 
