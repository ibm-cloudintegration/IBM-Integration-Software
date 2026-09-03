# IBM App Connect AI Agent lab

---

# Table of Contents

- [1. Overview](#overview)
- [2. IBM AppConnect Dashboard ](#ace-dashboard)
- [3. Sample prompts](#prompts)
- [4. Summary ](#summary)

---

## 1. Overview <a name="overview"></a>

In this lab, you will explore IBM App Connect Enterprise AI Agent capabilities from the IBM App Connect Dashboard. <br> 

**What is IBM App Connect Enterprise AI Agent?** 

The IBM App Connect Enterprise AI agent is an intelligent assistant built into IBM App Connect Enterprise (ACE) that helps teams manage, monitor, and connect enterprise integrations using natural language.

**Key Capabilities and Features** <br>

  - **Topology and Health Monitoring** <br>
    Instantly lists active or stopped integration runtimes, checks operational health status, and summarizes container environments without requiring command lines.
  - **Flow and Resource Inspection** <br>
    Inspects deployed message flows, surfaces dependencies, tracks policy requirements, and identifies deprecated components
  - **Deployment and Knowledge Guidance** <br>
    Provides actionable instructions for configuration changes across runtimes and queries pre-trained IBM knowledge bases for troubleshooting.
  - **Model Context Protocol (MCP) Integration** <br> 
    Uses the Model Context Protocol to turn existing APIs and connector actions into tools that external AI agents (like enterprise LLMs) can discover and invoke securely using everyday language

<br>
<!--
**High Level MQ AI Agent Topology** <br>
![alt text](./images/topology.png)
-->
<br>


## 2. IBM AppConnect Dashboard <a name="ace-dashboard"></a>

Follow below steps to ppen **IBM App Connect Dashboard**: <br>

Login to IBM Cloud Pak for Integration's Platform Navigator using the URL Provided. <br>

Right click on **ace-dashboard**, and click on **"Open Link in a New tab"**. <br>

![alt text](./images/image.png)

Click on **Open chat window**, the IBM MQ AI Assistent icon. <br>
![alt text](./images/image-1.png)

Accept the Disclaimer (if you see one). <br>
![alt text](./images/image-2.png)


A chat window will appear as below. <br>
![alt text](./images/image-3.png)



## 3. Sample prompts <a name="prompts"></a>

Run some sample prompts: <br>

1. What can the agent do for me?

![alt text](./images/image-4.png)

  Response: <br>
  ![alt text](./images/image-5.png)

2. Show me list of integration runtimes
![alt text](./images/image-6.png)

3. List the message flows under ace-tk-customerdb-v3 runtime
![alt text](./images/image-7.png)

4. Explain gen.CustomerDatabaseV3 message flow
![alt text](./images/image-8.png)

You can see more details if you scroll down in th chat window. <br>
![alt text](./images/image-9.png)


5. Are all the message flows are running?
This may take bit longer than the previous prompts, but you should see response. <br>
![alt text](./images/image-10.png)

5. What is IBM App Connect?

![alt text](./images/image-11.png)

6.  Similarly, run more prompts to explore the capabilities of App Connect AI Agent. <br>

<br>

## 4. Summary <a name="summary"></a>

Congratulations, you have explored IBM App Connect AI Agent and performed health checks of App Connect Deployments and the objects by issuing Natural Language Prompts. <br>
