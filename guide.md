# Datastreams
A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web and Mobile SDKs. Datastream is a configuration that defines how data is collected, processed, and sent to various destinations.

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
   
# Event Forwarding
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

3. **Select Service Type:** From the dropdown list, select **Event Forwarding** as the service type.

                                                   **Service Type**

4. **Map to Event Forwarding Property:** Choose your desired event forwarding property from the dropdown list to map it accordingly.

5. **Select Environment:** Specify the environment you wish to use for this service.
  
6. **Save Configuration:** Click **Save** to finalize and apply your service configuration.

# Schema
A schema is a set of rules that represent and validate the structure and format of data. At a high level, schemas provide an abstract definition of a real-world object (such as a person) and outline what data should be included in each instance of that object (such as first name, last name, birthday, and so on). XDM schemas are ideal for storing vast amounts of complex data in a self-contained format. You can have multiple schemas configured and choose the one that fits your use case. 

                                                   **Schema**

## Mapping the schema

### Steps:

1. **Create Data Schema:** Click on create schema and choose manual option. Further choose User, Event or other depending on what information you want to collect in your schema.
2. **Edit Data Schema:** Once your schema is created, you can also edit your schema using data fields. You can also choose where in schema you want your data fields. For this specific scenario, we required information like email, phone, fbc (facebook cookie) etc. These were added in different parts of the schema.

                                                   **Schema example**
   
You are ready to start creating rules in client side and server side after you have created the datastreams, created the property, configured the service and created the schema as per your use case. 

# Client Side Setup

## Websdk Extension

Begin by configuring the WebSDK extension on the client side. This extension facilitates the transmission of necessary parameters with the payload from the Adobe Edge server to platforms such as Facebook or Campaign Manager. The only required configuration required is **IMS Organisation ID and Datastreams** Set up the IMS Organisation ID and the datastreams you have configured. You can further configure other settings such as personalisation and identity settings as required. These settings will govern the type of data collected and the method of collection.

                                                   **Websdk Extension**

Upon completing the configuration, proceed to create global variables containing specific data within schemas intended for server-side transmission. It is essential to establish three primary rules:

1. **Global Data Object -** Define the global object or data that should accompany all server calls.

                                                   **Data Object**
   
2. **Global Data Variable -** Establish a variable that is updated and populated with specific data. This variable can be referenced similarly to other data elements.

                                                     **Data Variable**
3. **Global Merge Object -** Implement this data element to perform dual functions: transmitting the correct information to the server and updating the variable. It merges two data elements used in tandem.

                                                     **Merge Object**

In addition to the above three data elements, you should create data elements to capture the information required necessary for your ads platform. For example - Meta CAPI requires you to send a unique event id, fpc, fbp, user agent etc. CM API requires information like hashed email, hashed phone, GCLDC cookie etc to enhance the conversions. 

                                                     **Data Elements**

After you have created your data elements, you can create the rules to send data to server side. 

