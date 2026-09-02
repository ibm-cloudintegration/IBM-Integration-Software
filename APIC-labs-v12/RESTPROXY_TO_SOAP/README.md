#  IBM API Connect - Creating REST Proxy based upon a WSDL

[Return to main APIC lab page](../ReadMe.md#lab-abstracts)


---

# Table of Contents

- [1. Introduction](#introduction)
- [2. IBM App Connect - Deploy Temperature Converter WebService](#configure_oauth)
- [3. IBM API Connect - Create REST Proxy from the WSDL](#apic-create-api)
	* [3a. Add API](#apic-add-api)
	* [3b. Publish API](#apic-publish-api)
- [4. Testing REST Proxy Service](#test-api)
- [5. Summary](#summary)

---


# 1. Introduction <a name="introduction"></a>

In this lab, you will configure a SOAP WebService that is deployed to IBM App Connect to function as a REST Proxy within IBM API Connect. You will be deploying a very simple Temperature Converter WebService into IBM App Connect then expose it to IBM API Connect as a REST API.  <br>

<b> Design diagram </b>
<br>
![Alt text](./images/design-diagram.png)
<br>

# 2. IBM App Connect - Deploy Temperature Converter WebService <a name="ace-deploy"></a>

Download the bar file from [<b><u>here</u></b>](./src/TemperatureConverter.bar).

Deploy the bar file.<br>

Logon to Cloud Pak for Integration Platform Navigator, open App Connect Dashboard > Click on "Deploy Integrations" tile.<br>

![App Connect Dashboard](./images/image.png)

Select "Quick Start Integration", and Click \<Next\>. <br>

Drag & drop the bar file downloaded above as below.<br>
![Alt text](./images/image-1.png)

Click \<Next\> two times. <br>

Name your Integration Runtime as \"ace-tk-temperature-converter\". <br>

![Alt text](./images/image-3.png)

Click \<Create\>. <br>

Wait for 30seconds and refresh the page. <br>

Make sure the Integration Runtime \"ace-tk-temperature-converter\" is Ready. <br>

Click on the Integration Runtime \"ace-tk-temperature-converter\" tile.<br>

![Alt text](./images/image-13.png)

![Alt text](./images/image-14.png)

Click on the Properties tab, and copy "SOAP HTTP URL". This will be configured in the next section (API Creation).<br>


![Alt text](./images/image-12.png)

<br>


# 3. IBM API Connect - Create REST Proxy from the WSDL <a name="apic-create-api"></a>

Download the zip file that contains Temperature Converter WSDL, and XSD's from [<b><u>here</u></b>](./src/TemperatureConverter_WSDL.zip).

Logon to Cloud Pak for Integration, and open API Management (apim-demo). <br>

Click on "API Studio" icon.<br>

![Alt text](./images/image-2.png)

Click on "New API Project > Create a new project".<br>

![Alt text](./images/image-4.png)

Enter **"Project name"** as **"student(n)-soap-project"**, and  "Description" as **"TemperatureConverter - SOAP to REST".** <br>

![alt text](./images/image-4a.png)



## 3a. Add API <a name="apic-add-api"></a>

Click on the project you just created. <br>
![alt text](./images/image-4b.png)

Click on **"Add API"**. <br>
![alt text](./images/image-4c.png)

Select **SOAP**. <br>
![alt text](./images/image-4d.png)

Drag and drop the zip file that you downloaded above. <br>

![alt text](./images/image-4e.png)

Enter **API Name** as **student1-temperature-converter-rest-api**, then click **\<Create\>**. <br>
![alt text](./images/image-4f.png)

Copy the highlighted **path** value (Control+c). We need update this value in the two yml files highlighed below.<br> 

![alt text](./images/image-4g.png)

Notice that it's missing part of the zip file. **its a bug, will be fixed**<br>
![alt text](./images/image-4h.png)

Paste here. <br>
![alt text](./images/image-4i.png)

Similarly, update next **yml** file as below. <br>
![alt text](./images/image-4j.png)

Click on the **Design** view. <br>

![alt text](./images/image-4k.png)


Click **Policy Sequence**, and then click **assembly**. <br>

![alt text](./images/image-4l.png)

Close the Policies view. <br>

![alt text](./images/image-4m.png)

Click on the "Invoke" policies and set the URL that you captured in the IBM App Connect section. <br>

![alt text](./images/image-4n.png)


## 3b. Publish API <a name="apic-publish-api"></a>

Click **Publish**. <br>

![alt text](./images/image-5.png)

Click \<Next\> in the bottom right of of the screen. <br>

![Alt text](./images/image-6.png)

Click \<Publish\> in the bottom right of of the screen. <br>

![Alt text](./images/image-7.png)

If Publish is successful, then click on **Catalog**. <br>

![Alt text](./images/image-8.png)

Click \<Catalog settings\> tab, then click on **Portal**.<br>

![Alt text](./images/image-9.png)

<br>

# 4. Testing REST Proxy Service<a name="test-api"></a>


Click on the "API Products" tab.<br>
![alt text](./images/image-15.png)

Click on student(n)-temperature-converter-rest-api-product. <br>
![alt text](./images/image-16.png)

Click **\<Subscribe\>**. <br>
![alt text](./images/image-17.png)

Select **Create new subscription**, then click **Request**. <br>
![alt text](./images/image-18.png)

![alt text](./images/image-19.png)

Click on soap-demo application. <br>
![alt text](./images/image-20.png)

Click on the API. <br>
![alt text](./images/image-21.png)

![alt text](./images/image-22.png)

Select **API Resources** > **/CtoF** > **GET**, then click **\<Try\>** button. <br>
![alt text](./images/image-23.png)

Enter a Centigrade value, and cick **\<Send\>**. <br>
![alt text](./images/image-24.png)

You should get the response with the Converted Fahrenheit value as below.<br>

![alt text](./images/image-25.png)


**Optional test:** You can also try POST CtoF operation and enter below in the Body tab. <br>


# 5. Summary<a name="summary"></a>


Congratulations, you have exposed a SOAP WebService deployed on IBM App Connect to IBM API Connect as an REST API. <br> <br>

[Return to main APIC lab page](../ReadMe.md#lab-abstracts)

