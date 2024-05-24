# Smart Refrigerator IoT Application

## Table of Contents
1. [Introduction](#introduction)
2. [Cloud Architecture Flow Diagram](#cloud-architecture-flow-diagram)
3. [Cloud Services](#cloud-services)
4. [IoT Application Security Considerations](#iot-application-security-considerations)
5. [DevOps Testing Strategies](#devops-testing-strategies)
6. [References](#references)

## Introduction

**Home Application:**  
“Connected fridge-freezer with various sensors such as temperature, and capability to auto-order items”

Multimedia-capable intelligent appliances have been making their way into our daily lives. The rapid advancement of computer technology and the widespread usage of the Internet have made the smart home one of the most well-known applications for intelligent appliances. One area where such sophisticated appliances have been used is the kitchen. Given that the consumer must buy the entire refrigerator, the existing products are pricey. Any existing refrigerator can be transformed into an intelligent, affordable appliance utilizing sensors using the Smart Refrigerator module. The recipe is displayed on an LCD in a previously set method based on the ingredients that are now in the refrigerator. Our refrigerator has the ability to sense and monitor its contents. It can also remotely alert the user via an Android application when certain products are running low. By including a link to the internet retailer of that specific item, it also makes it easier to buy rare products (Velasco et al., 2020).

The Internet of Things (IoT) concept necessitates ubiquitous connectivity to billions of disparate devices. Recent years have seen a tremendous increase in IoT devices in the context of smart homes, which has envisioned a wide range of unique services and uses. A smart home's kitchen is one of the most crucial rooms since it includes numerous appliances that improve household services. Our project is centered on the smart refrigerator. There have been numerous attempts to construct the smart refrigerator, but none of them have proven financially or energy-efficient. The user is unable to maintain track of the food items in the refrigerator due to modern living and the fast-paced surroundings (Mahajan et al., 2017).

Despite the industry's efforts to create a smart refrigerator, the present or existing technology is still not economical or energy-efficient. For a typical household user who is unfamiliar with the intricate workings of the smart refrigerator, the technology is either too sophisticated or confusing. Most locations still have inadequate internet connectivity, and there is little network connectivity, either in the form of slow internet speeds or bad assistance. The crucial information about the goods, such as the expiration date, is not uniformly recorded by the barcode. The networked home or smart home environment lacks sufficient security to prevent data leaks from the house. Attackers may jeopardize the user's and the home's privacy. The smart system can be controlled by remote devices using any operating system. Since there is no industry standard, different companies produce goods that adhere to different standards. The internet refrigerator, often known as a smart refrigerator, is used to track the contents and provide alerts when certain foods become scarce. When energy conservation is possible, offer ON/OFF control through cell phone, etc. The concept of internet-connected home appliances or the smart home environment has long been considered to be the future and the next big thing (Fujiwara et al., 2018).

The Internet of Things (IoT) is a global network of interconnected computing devices, mechanical and digital machinery that may exchange data over a network without requiring human-to-human or human-to-computer contact. A collection of specialized transducers with a communications network for monitoring and recording conditions at various locations makes up a wireless sensor network. The creation of smart refrigerators has been the subject of prior investigations. The Intelligent Refrigerator made use of infrared (IR) emitters to identify the products and alert the user via SMS and the shop owner via Ethernet network of the state of the products inside the refrigerator. The Smart Refrigerator measures the weight of the items within the refrigerator using a weight sensor or load cell. Through Bluetooth, it alerts the user to its status. The Smart Fridge employed a photodiode and a Node MCU, respectively, as the sensor to detect the product and the microcontroller to handle the sensor's data. A refrigerator with an overhead camera that recognizes faces to provide users access and utilizes RFID to find and track the contents is used to store medical supplies online. The Low-Cost Smart Refrigerator, on the other hand, utilized a camera to take images of the food within the refrigerator, an IR distance sensor, and a light sensor to determine if the refrigerator was open or closed (Mani et al., 2020).

The smart refrigerator uses image processing to recognize the inventories and things inside the appliance, however because the recognition was carried out using template matching, the image processing component crashed. Next, the High Chest smart freezer was created to support energy conservation and appropriate food storage. A system for managing products was suggested to keep track of perishable and non-perishable goods using GSM and Android applications (Saidur, Masjuki, and Choudhury, 2002).

A customized Coke machine at Carnegie Mellon University served as the first internet-connected appliance, reporting its inventory and the temperature of freshly loaded drinks. The idea of a network of smart devices was initially suggested in 1982. Through the Auto-ID Center at MIT and related market study publications, the idea of the internet of things first gained popularity in 1999. Kevin Ashton, one of the original Auto-ID Center founders, believed that radio-frequency identification (RFID) was necessary before the internet of things could exist. If every person and thing in daily life had an identification, then computers could manage and keep track of them. In addition to using RFID, near field communication technology can be used to tag objects (Suhuai Luo, Jin, and Li, 2009).

The concept of tying home appliances to the internet (Internet of Things) had gained popularity and was regarded as the upcoming big thing by the late 1990s and early 2000s. The Internet Digital DIOS, the first internet-connected refrigerator, was introduced by LG in June 2000. A refrigerator that has been designed to detect the types of goods being stored inside it and keep track of the stock by barcode or RFID scanning is referred to as an "Internet refrigerator" (also known as a "Smart refrigerator"). This type of refrigerator frequently has the capability to recognize when a food item requires replenishment. Given that it cost more than $20,000 and was perceived by consumers as being unnecessary, as well as the fact that the problems it claimed to answer were vague, this refrigerator was a failure. For instance, many juice bottles are transparent, serving as a visual cue that a purchase will eventually be necessary. Similarly, vegetable drawers are transparent and frequently contain items that have been removed from packages, eliminating the need for bar codes in inventory, which required manually entering descriptions and dates. Additionally, it is not often possible to solve the use case of the gadget being able to notify users of forthcoming purchases when there are frequently numerous buyers in a household that interact informally (James, Onarinde, and James, 2016).

By 2013, the Internet of Things' original concept had changed as a result of the convergence of several technologies, including wireless communication, the Internet, embedded systems, and microelectromechanical systems (MEMS). As a result, the conventional domains of automation (including home and building automation), wireless sensor networks, control systems, embedded systems, and others all contribute to enabling the internet of things (IoT). The Internet of Things (IoT) is a network of interconnected computing devices, mechanical and digital machinery, and people that may exchange data over a network without requiring human-to-human or human-to-computer contact. A collection of specialized transducers with a communications network for monitoring and recording conditions at various locations makes up a wireless sensor network (Patel, Patel, and Scholar, 2016).

The study's overarching goal is to build a sensor network-based IoT-based refrigerator inventory monitoring system that will inform the user of the contents of the refrigerator.

## Cloud Architecture Flow Diagram

The architecture diagram of the IoT device used in this application is:

![Cloud Architecture Flow Diagram](https://github.com/afzaaljavaid47/IOT-Based-Applications/blob/master/Fridge%20Freezer%20Automation%20System%20Using%20Azure%E2%80%99s%20IOT%20service/Flow%20Diagram.drawio.png)

### Flows of Application
- Fridge Freezer IoT Device to IoT Hub
- IoT Hub Trigger Azure Function to Azure SQL Database
- HTTP Trigger Azure Function from SQL Database to Web App
- IoT Hub Trigger to HTTP Trigger Event Call
- Conditional Auto Order Flow
- Control App Device to IoT Hub

### 2.1 Fridge Freezer IoT Device to IoT Hub
In this flow, the sensor device circuit (IoT Device) that is installed in the fridge freezer will generate the data (Temperature, Items Details etc.), and then generated data sent to Azure IoT Hub.

### 2.2 IoT Hub Trigger Azure Function to Azure SQL DB
“IoT Hub Trigger Azure Function” is a type of Azure Function that will trigger when Azure IoT Hub receives any data from the Fridge Freezer IoT Device. We will transform the data into a specific schema and pass the data to the SQL API that will save the data to the Azure SQL Database.

### 2.3 HTTP Trigger Azure Function from SQL DB to Web App
“HTTP Trigger Azure Function” is a type of serverless function that will trigger when an HTTP request is called. It will get data from the Azure SQL Database using the SQL API. Then we will call this “HTTP Trigger Azure Function” in our Frontend Framework (React) that will visualize the data in graphs and charts etc.

### 2.4 IoT Hub Trigger to HTTP Event Call
When a specific event occurs like temperature increase beyond a given limit, an automatic event occurs like lowering the temperature or shutting down the fridge etc. will occur and the event data will pass from the IoT Hub Trigger Azure Function that will update the event and call the Azure IoT Hub and update the Fridge Freezer IoT Device.

### 2.5 Conditional Auto Order Flow
When a specific event occurs like any item is not available in the Fridge and is out of stock, then this event will call the Azure Function that will place the order of that specific item using an HTTP Post request to a specific vendor.

### 2.6 Control App Device to IoT Hub
We can use the Azure IoT Hub Direct Method to call the IoT Hub from a web app like the Azure Function and control the device like Turn Off Fridge or Turn On Fridge Freezer etc.

## Cloud Services

### 3.1 Azure IoT Hub
The data generated from the IoT Device is sent to Azure IoT Hub.

### 3.2 Azure Functions
The Azure IoT Hub Trigger Function triggers whenever data is received. Data transformation is applied to the data and then data is sent to Azure SQL DB. The HTTP Trigger Azure Function will trigger when HTTP requests occur.

### 3.3 Azure SQL Database
The data is stored in Azure SQL Database.

### 3.4 Azure Web App
A React web app is hosted to visualize the data in graphs and charts etc.

## IoT Application Security Considerations

### 4.1 Authentication and Authorization
- Use Azure Active Directory (AAD) to manage users and permissions.
- Implement role-based access control (RBAC).

### 4.2 Data Encryption
- Use HTTPS for data in transit.
- Enable Transparent Data Encryption (TDE) for data at rest in Azure SQL Database.

### 4.3 Secure Communication
- Use VPNs or private connections to secure communication between IoT devices and the cloud.

### 4.4 Regular Updates and Patching
- Keep the IoT firmware and cloud services up to date with the latest security patches.

### 4.5 Network Security
- Use firewalls and network security groups to restrict access to cloud resources.

## DevOps Testing Strategies

### 5.1 Continuous Integration/Continuous Deployment (CI/CD)
- Implement CI/CD pipelines using Azure DevOps or GitHub Actions.

### 5.2 Automated Testing
- Unit Tests: Ensure individual components work correctly.
- Integration Tests: Verify end-to-end functionality.
- Load Testing: Test system performance under heavy load.

### 5.3 Monitoring and Logging
- Use Azure Monitor and Application Insights to track performance and errors.
- Implement logging for critical events and system errors.

### 5.4 Security Testing
- Conduct regular penetration testing.
- Use automated tools to scan for vulnerabilities.

## References

- Velasco, J., Abad, A., & Rubio, B. (2020). Intelligent Refrigerators and Internet of Things. Journal of Smart Home Development.
- Mahajan, R., et al. (2017). IoT-based Smart Refrigerator. Journal of Home Appliance Studies.
- Fujiwara, Y., et al. (2018). Efficient Smart Refrigerator Systems. Journal of Energy Efficient Appliances.
- Mani, V., et al. (2020). Low-Cost Smart Refrigerators for Modern Homes. Journal of Modern Home Innovations.
- Saidur, R., Masjuki, H. H., & Choudhury, I. A. (2002). Technologies to Improve Energy Efficiency in Refrigerators. Journal of Energy Conservation.
- James, S. J., Onarinde, B. A., & James, C. (2016). The Internet of Things for Smart Refrigeration. Journal of Smart Appliances.
- Patel, K. K., Patel, S. M., & Scholar, P. (2016). Internet of Things-IoT: Definition, Characteristics, Architecture, Enabling Technologies, Application & Future Challenges. Journal of International Scientific Research.
- Suhuai Luo, Jin, X., & Li, H. (2009). Development of a Smart Refrigerator. Journal of Embedded Systems and Applications.

###

## ✴️: Development Languages

1. **Programming languages** : .NET
2. **Tools** : Visual Studio, Azure Functions, Internet of Things
   
###

