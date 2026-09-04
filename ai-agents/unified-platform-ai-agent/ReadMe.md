# IBM Integration Platform AI Agent lab

---

# Table of Contents

- [1. Overview](#overview)
- [2. IBM Unified Integration Platform Navigator](#int-platform)
- [3. Sample prompts](#prompts)
- [4. Summary ](#summary)

---

## 1. Overview <a name="overview"></a>

In this lab, you will explore IBM Integration Platform AI Agent Capabilities. <br>

**What is IBM Integration Platform AI Agent?** 
IBM Integration AI Agent is a conversational, AI-powered feature in the Platform UI that helps administrators diagnose, monitor, and troubleshoot hybrid integration environments using natural language queries. <br>

**Core Components & Specialized Agents** <br>
The system uses a unified Supervisor Agent that coordinates multiple specialized background agents:. <br>

- **Knowledge Agent**
Queries official documentation, product guides, and support content to provide personalized guidance.
- **Log Agent** <br>
Scans and analyzes component logs for warnings and errors.
- **Topology Agent**
Maps out how software instances relate to Kubernetes objects and resources.
- **Instance Agent**
Checks and reports on the operational health and status of deployed instances and containers.
- **Versions and Updates Agent**
Proactively checks component currency and available software fixes.

**Key Benefits** <br>
- **Faster Troubleshooting**
Cuts down time spent manually searching raw log files and complex documentation.
- **Lower Barrier to Entry**
Helps teams manage Kubernetes and integration topologies without requiring deep specialist expertise.
- **Maintains Human Control**
Acts as a guided assistant while leaving administrators fully responsible for final decisions and execution

<br>

**High Level Integration AI Agent Topology** <br>
![alt text](./images/topology.png)

<br>


## 2. IBM Unified Integration Platform Navigator <a name="int-platform"></a>

Login to IBM Cloud Pak for Integration's Platform Navigator using the URL Provided, and click on the **AI** icon on the top right of the screen. <br>

![alt text](image.png)

Accept the Disclaimer if you see one. <br>

![alt text](image-1.png)

A chat window should be opened. <br>
![alt text](image-4.png)

<br><br>

## 3. Sample prompts <a name="prompts"></a>

Run some sample prompts: <br>

1. Click on **"Health check my Cloud Pak for installation**. <br>

![alt text](image-2.png)

You should see details about the installation, and recommendations as you can see below that a newer Operator is available. <br>

![alt text](image-3.png)

2. What can you help me with? <br>

![alt text](image-5.png)

3. Create yaml to create nativeha queue manager? <br>

![alt text](image-6.png)

<br>

4. Similarly, run additional prompts <br>
<br>


## 4. Summary <a name="summary"></a>

Congratulations, you have explored IBM MQ Agent and performed health checks of MQ Queue Managers and the objects by issuing  prompts. <br>
