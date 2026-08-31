# IBM API Connect

## Add OAuth Security to your API and use Lifecycle Controls to Version Your API

[Return to main APIC lab page](../ReadMe.md#lab-abstracts)

Lab prerequisite: "Create and Secure an API with DataPower API Gateway"

---

# Table of Contents

- [1. Introduction](#introduction)
- [2. Configure OAuth Security](#configure_oauth)
	* [2a. Configure Authentication URL User Registry](#configure_registry)
- [3. Create an OAuth Service](#create_oauth_service)
- [4. Add the OAuth Service to the Sandbox Catalog](#add_service)
- [5. Update customer-database-agw API](#update-api)
	* [5a. Add OAuth Security](#oauth_customer)
- [6. Publish API](#publish-api)
- [7. Test OAUTH Security](#test_oauth)
- [8. Test the OAuth Configuration](#test_oauth)

---

# 1. Introduction <a name="introduction"></a>

In this lab, we will secure the Customer Database API that was created in the "Create and Secure an API with DataPower API Gateway" lab to protect the resources exposed by IBM API Connect. Consumers of our API will be required to obtain and provide a valid OAuth token before they can invoke the Customer Database API. 

**Pre-Requisite:** Finish **Create and Secure an API with DataPower API Gateway** before this. <br>

# 2. Configure OAuth Security <a name="configure_oauth"></a>

IBM API Connect is a full-featured OAuth 2.0 provider. The OAuth exchange works like any other API call, and thus we treat it as its own API.

In this section, you will create a new OAuth provider API, configure which grant type to use, and configure how it will authenticate user credentials.

# 2a. Configure Authentication URL User Registry <a name="configure_registry"></a>

In order to configure user authentication, you must first define the **Registry** to use, which may be **LDAP**, **local user registry**, or an **authentication URL**. For this lab, you will implement an Authentication
URL.

1\.If you're not logged before, follow these instructions to access to the API Manager -> [Login to the API Manager](../APIC-prereq/Login-apic/index.md)

2\. In the left menu, click on **Resources**.  As you hover over the icon, you will see the item name.

![alt text](./images/image.png)

3\. Make sure **User registries** is selected and click **Create**.

![alt text](./images/image-1.png)

4\. Click on **Authentication URL user registry**.

![alt text](./images/image-2.png)


5\. Enter **Student(n) App Registry** for the **Title**, **https://httpbin.org/basic-auth/student(n)/passw0rd** for the **Url**, and **App Registry** for the **Display name**.  Click **Save**.<br>
Note: Make sure to replace student(n) with your student number. Example student1 <br>

![alt text](./images/image-3.png)


# 3. Create an OAuth Service <a name="create_oauth_service"></a>

1\. You should still be in **Resources**.  If not, in the left menu, click **Resources**. Click on **OAuth providers**. <br>

![alt text](./images/image-5.png)


2\. Click **Add** and select **Native OAuth provider** from the drop down.

![alt text](./images/image-6.png)


3\. Enter **student(n)-oauth** for the **Title** and select **DataPower API Gateway** for the **Gateway Type**.  Click **Next**.

![alt text](./images/image-7.png)


4\. The Configuration screen will show the default Authorize and Token paths.  For **Supported grant types**, select **Resource owner - Password** and deselect **Access code**.  For **Supported client types**, select **Confidential**.  Click **Next**.

![alt text](./images/image-8.png)


5\. One scope, **sample&#95;scope&#95;1**, is automatically created.  


![alt text](./images/image-9.png)

6\. Replace **sample&#95;scope&#95;1** with **customer** for Scope **Name** and replace **Sample scope definition 1** with **Access to Customer API** for Scope **Description**.  Click **Next**.

![alt text](./images/image-9a.png)

7\. Accept the defaults (**App Registry** for **Authenticate application users using**) and click **Next**.

![alt text](./images/image-9b.png)

8\. Review the OAuth configuration and click **Finish**.

![alt text](./images/image-9c.png)


9\. Click **Save**.

![alt text](./images/image-10.png)


# 4. Add the OAuth Service to the Sandbox Catalog <a name="add_service"></a>

1\. In the left menu, click on **Manage**.

![alt text](./images/image-11.png)


2\. Click on **Sandbox**

![alt text](./images/image-12.png)

3\. In the top menu, click on **Catalog settings**.

![alt text](./images/image-13.png)


4\. Click on **API user registries**.

![alt text](./images/image-14.png)


5\. Click **Edit**.

![alt text](./images/image-15.png)


6\. Select **Student(n) App Registry** and click **Save**.

![alt text](./images/image-16.png)


7\. Click on **OAuth providers**.

![alt text](./images/image-17.png)

8\. Click **Edit**

![alt text](./images/image-18.png)


9\. Select **student1-oauth** and click **Save**.

![alt text](./images/image-19.png)


# 5. Update customer-database-agw API <a name="update_api"></a>

1\. In the left menu, click on **API Studio**.

![alt text](./images/image-20.png)

Select customer-database-agw project. <br>

![alt text](./images/image-21.png)

Click on your API, customer-database-agw. <br>

![alt text](./images/image-22.png)

Scoll down to Components section, then click on \<Add a new security schema\>. <br>

![alt text](./images/image-23.png)


## 5a. Add OAuth Security <a name="oauth_customer"></a>

1\. Select oauth-2, then enter Security schema key as **oauth-1**.

![alt text](./images/image-24.png)

Click \<Add\>. <br>

2\. For the **"Catalog"** select **Sandbox**, for the **"OAuth Provider"** select **student1-oauth**, for the **Scope" select **"Resource Owner - Password"**. <br>

![alt text](./images/image-25.png)

Scroll down, and you should see the **"customer"** scope, and it should select automatically. <br>

![alt text](./images/image-26.png)


3\. Add **oauth-1** to the API Security. Click **\<Security\>** tab.

![alt text](./images/image-27.png)

Click **\<Add security schema\>**. <br>
![alt text](./images/image-28.png)

Select **oauth-1**, then click \<Add\>.
![alt text](./images/image-29.png)

You should see **oauth-1**, along with **ClientID, Secret**. <br>
![alt text](./images/image-30.png)

So, your API is now protected with multiple securities and the API consumers can use either security. <br>

Now, select **customer** scope as below. <br>
![alt text](./images/image-31.png)



# 6. Publish the API <a name="publish-api"></a>

![alt text](./images/image-32.png)

![alt text](./images/image-33.png)

![alt text](./images/image-34.png)



# 7. Test OAUTH Security<a name="test_oauth"></a>

In this section, you will test the API to ensure that OAuth is working properly. <br>

Login the Dev Portal with your studentid, and password that you created in the first lab. <br>

![alt text](./images/image-35.png)

<!--
Click on customer-database-agw product. <br>

![alt text](./images/image-36.png)
-->

Click on Applications. <br>

![alt text](./images/image-37.png)

Click on the **demo-app** that you created and subscribed to customer-database-agw product/api. <br>
![alt text](./images/image-38.png)

We will use the **Client Id, Client Secret** next to obtain OAUTH Bearer Token. <br>
![alt text](./images/image-39.png)

**SAVE**  ClientID, Secret into a Notepad or Textpad. <br>

Now, let's capture the TOKEN URL. <br>

Click on the API Name. <br>

![alt text](./images/image-40.png)

Copy the highlighted section of the Endpoint URL (upto Sanxbox) and save to Notepad. <br>

![alt text](./images/image-41.png)

So you should have captured CLIENTID, SECRET, and part of the Endpoint URL. We will use them the below curl command<br>

<!--
21a\. TESTING WITH CURL (Optional)

** From the developer portal **
** Copy the GET /customers URL and save to Scratchpad or Notepad. ** <br>
** Copy the "token url" and save to Scratchpad or notepad.**
-->

Open a **Terminal** or **Command Line** window.<br>

**Get Bearer Token:** <br>

Copy the below curl command into the Terminal, and replace Client ID, and Secret, and endpoint URL from the above. <br>

```
curl -k -X POST -d "grant_type=password&client_id=REPLACE_WITH_YOUR_CLIENT_ID&client_secret=REPLACE_WITH_YOUR_CLIENT_SECRET&username=student(n))&password=passw0rd&scope=customer" REPLACE_WITH_YOUR_TOKEN_URL/student(n)-oauth/oauth2/token
```

<br>
EXAMPLE:
curl -k -X POST -d "grant_type=password&client_id=xxxxxx&client_secret=yyyyyy&username=student1&password=passw0rd&scope=customer" https://apim-demo-gw-gateway-cp4i-apic.apps.itz-xxxxx.infra01-lb.dal14.techzone.ibm.com/sbodapati-porg/sandbox/student1-oauth/oauth2/token
<br>
Output should look like below: <br>

![alt text](./images/image-42.png)

Now, from the Developer Portal, copy the customer-database-agw Endpoint basepath. <br>

![alt text](./images/image-43.png)

Now copy the below curl command into the Terminal window and update with the Bearer token and the endpoint url appending /customers to the endpoint URL.

```
curl -k -H "Authorization: Bearer REPLACE_WITH_YOUR_BEARER_TOKEN_FROM_ABOVE" REPLACE_WITH_GET_CUSTOMERS_URL
```

Example URL:  <br>
curl -k -H "Authorization: Bearer AAIgNWU5OGRiYjEzNGU3ZDJlOGQ5NjBjZTlgPl5hj59Dl2tuPTQ_RTfE2BjgYOa1unWWlatdflfw0SYRbX_14TiXQG_u_hPT1cWy3DtvA" https://apim-demo-gw-gateway-cp4i-apic.apps.itz-xxxxx.infra01-lb.dal14.techzone.ibm.com/sbodapati-porg/sandbox/ace-tk-customerdb-v3-http-cp4i-ace.apps.itz-xxxxxx.infra01-lb.dal14.techzone.ibm.com/customerdb/v3/customers


![alt text](./images/image-44.png)

You should see the customers. <br>

22\. Feel free to test the rest of the operations.  Testing will be similar to the testing that was completed in the "Create and Secure an API to Proxy an Existing REST Web Service" lab.

23\. To prove that the token is being validated, you can modify the contents of the **Access Token** field. Click **Send** again and you will see an error response.  **Note:** Modifying the beginning of the token will throw a **Client id missing** error.  Modifying the middle or end of the token will throw the error below.



## 8. Summary<a name="summary"></a>

Congratulations, you have completed the **Add OAuth Security to your API and use Lifecycle Controls to Version Your API** lab. Throughout the lab, you learned how to:

-   Configure an OAuth 2.0 service with the Resource Owner Password grant type

-   Secure your API with OAUTH

-   Tested your API with OAUTH

[Return to main APIC lab page](../ReadMe.md#lab-abstracts)
