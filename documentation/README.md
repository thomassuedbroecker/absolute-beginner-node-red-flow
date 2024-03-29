# Introduction

This [Node-RED](https://nodered.org/) flow is for **absolute beginners** with minimal [`Javascript`](https://www.w3schools.com/js/DEFAULT.asp) programming knowledge, who plan to participate in Hackathons.

**Here a 25 min guide and overview on YouTube**

[![Absolute beginner Node-RED flow (2021)](https://img.youtube.com/vi/qtOmufIjafE/0.jpg)](https://www.youtube.com/watch?v=qtOmufIjafE "Click play on youtube")

### Questions

The documentation guides you to following main topics in Node-RED:

How to ...

* ... save data in a database?
* ... search for entries in a database?
* ... display data in a UI?

The flowing gif shows the usage of final flow implementation in Node-RED.

![](./images/absolute-beginner-example.gif)

### Motivation

The motivation for that example project is: When I support Hackathons I notice there's often a lack of programming knowledge and building UIs. If this is the case, then Node-RED is a perfect starting point to realize a prototype at a hackathon.
The **dashboard** of Node-RED is an awesome way to build a UI, but there was a _"out of the box"_ Node missing to simply to add a **table**. Now I found a very useful Node that’s create a table inside a Node-RED dashboard.

That’s motivated me to create this example project, which provides an example to build a simple application from scratch, which contains the main functionalities to insert data, display data in a table and search for values, as you see in the gif below.

![](./images/absolute-beginner-ui.gif)

### Estimated time and level

|  Time | Level | Topic |
| - | - | - |
| 15 min | beginners | prerequisites |
| 30 min | beginners | (option 1) build flow absolute beginner from scratch |
| 10 min | beginners | (option 2) import existing absolute beginner flow |

### Objectives

After the setup of the example should be able to use your Node-RED instance on IBM Cloud to

* ... save data in a [Cloudant database](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-databases) within your Node-RED installation on IBM Cloud
* ... search for data entries using [Cloudant database query](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-query)
* ... display data in a UI using [Node-RED dashboard](https://flows.nodered.org/node/node-red-dashboard) and [Node-RED UI Table](https://flows.nodered.org/node/node-red-node-ui-table)

### Architecture

The following diagram shows the simplified architecture of the example Node-RED application. 

![](./images/simplified-architecture.png)

### Prerequisites

You should have a ...

* ... free [IBM Cloud Lite Account](https://cloud.ibm.com/docs/overview?topic=overview-quickstart_lite) and upgraded to an [PayAsYouGo Account](https://cloud.ibm.com/docs/account?topic=account-accounts)
* ... running Node-RED instance on IBM Cloud created with a pre-configured Node-RED App.
![](../images/node-red-ibm-cloud-app.png)

### Additional resources

* [Setup Node-RED on IBM Cloud](https://suedbroecker.net/2020/03/09/a-short-introduction-of-the-node-red-starter-kit-on-ibm-cloud-for-hackathons/)
* [Handle CORS in your Node-RED instance on IBM Cloud](https://suedbroecker.net/2019/03/13/cors-and-node-red-using-a-simple-forward-server/)
* [REST endpoints, authentication to external API, extract data from API, customize data and CRUD](https://suedbroecker.net/2020/03/26/a-node-red-twitter-follower-flow/)
