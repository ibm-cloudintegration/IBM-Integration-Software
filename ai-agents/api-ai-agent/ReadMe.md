# IBM API Connect AI Agent lab

---

# Table of Contents

- [1. Overview](#overview)
- [2. IBM AppConnect Dashboard ](#ace-dashboard)
- [3. Sample prompts](#prompts)
- [4. Summary ](#summary)

---

## 1. Overview <a name="overview"></a>

In this lab, you will explore IBM API Connect AI Agent capabilities from the IBM API Connect Dashboard. <br> 

**What is IBM API Connect Enterprise AI Agent?** 

The IBM API Connect Enterprise AI Agent (API Agent) is an intelligent assistant built into IBM API Connect that helps developers design, govern, test, publish, and manage APIs using natural language. Powered by watsonx.ai and built on an agentic framework, it automates key tasks across the API lifecycle, including API creation, documentation, governance validation, testing, and deployment, enabling teams to deliver AI-ready APIs faster while maintaining enterprise standards and security.

**Key Capabilities and Features** <br>

  - **Natural language API development:** <br>
    Describe an API requirement in plain English and the agent can generate OpenAPI specifications, documentation, and mock responses.
  - **API discovery and reuse:** <br>
    Searches existing API catalogs to identify reusable APIs and reduce API sprawl.
  - **Governance and compliance:** <br>
    Validates APIs against organizational standards and can automatically remediate governance issues.
  - **Automated testing:** <br>
    Generates and executes API test cases based on API semantics and expected behavior.
  - **Code-first and design-first support:** <br>
    Works with both development approaches and can help generate backend application code and deployments.
  - **Conversational experience:** <br>
    Uses a chat-based interface to plan, execute, and explain actions while requiring approval for system-changing operations.

<br>
<!--
**High Level MQ AI Agent Topology** <br>
![alt text](./images/topology.png)
-->
<br>


## 2. IBM API Connect Dashboard <a name="ace-dashboard"></a>

Follow below steps to open **IBM API Connect Dashboard**: <br>

Login to IBM Cloud Pak for Integration's Platform Navigator using the URL Provided. <br>

Right click on **apim-demo*, and click on **"Open Link in a New tab"**. <br>

![alt text](./images/image-1.png)

Click on **AI**, in the upper right corner to open the API Assistant chat window. <br>
![alt text](./images/image-2.png)

A chat window will appear as below. <br>
![alt text](./images/image-3.png)



## 3. Sample prompts <a name="prompts"></a>

1. First lets explore some of the Sample prompts.   Click on the **hamburger icon**

![alt text](./images/image-4.png)

You will see a list of Sample Prompts you can run. <br>

![alt text](./images/image-5a.png)

  Response: <br>
  ![alt text](./images/image-5.png)

2. Show me list of integration runtimes
![alt text](./images/image-6.png)

5.  Similarly, run more prompts to explore the capabilities of API Connect AI Agent. <br>

<br>

## 4. Summary <a name="summary"></a>

Congratulations, you have explored IBM API Connect AI Agent and performed health checks of API Connect Deployments and the objects by issuing Natural Language Prompts. <br>
