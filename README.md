# Simple Data Pipe 

:no_entry_sign: This project is no longer maintained.

The Simple Data Pipe is an app that loads data from cloud data sources into Cloudant, IBM's managed NoSQL database. Out of the box you can load data from salesforce.com and stripe.com. You can load data from other cloud data sources, such as Reddit using [custom connectors] (https://developer.ibm.com/clouddataservices/simple-data-pipe-connectors/).

## Usage
To use the Simple Data Pipe, grab the code on Github, and then deploy it to IBM Bluemix, where it runs. It lives at a URL in Bluemix, and comes complete with an AngularJS UI for connecting, scheduling, and reporting. 

To follow our full tutorial please visit : https://developer.ibm.com/clouddataservices/simple-data-pipe/

## Deploy to IBM Bluemix

The fastest way to deploy this application to Bluemix is to click the **Deploy to Bluemix** button below. If you prefer instead to deploy manually to Bluemix then read the entirety of this section.

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy?repository=https://github.com/ibm-cds-labs/simple-data-pipe)

If you:
<ul>
<li><strong>don't have a Bluemix account</strong>,  you'll be prompted to <a href="http://www.ibm.com/cloud-computing/bluemix/" target="_blank">sign up</a>.  Create your account, verify your email address, then return here and click the the <strong>Deploy to Bluemix</strong> button again. </li>
<li><strong>have trouble deploying</strong>, make sure you haven't already reached your Bluemix memory and services quotas. You get 10 services with your account's free trial period. If you have questions about working in Bluemix, find answers in the <a href="https://www.ng.bluemix.net/docs/" target="_blank">Bluemix Docs</a>.</li>
</ul>

### Configuring Cloud Foundry

Complete these steps first if you have not already:

1. [Install the Cloud Foundry command line interface.](https://www.ng.bluemix.net/docs/#starters/install_cli.html)
2. Follow the instructions at the above link to connect to Bluemix.
3. Follow the instructions at the above link to log in to Bluemix.

### Creating Backing Services

Create a Cloudant service within Bluemix if one has not already been created:

    $ cf create-service cloudantNoSQLDB Lite sdp-cloudant-service

Create a Single Sign On (SSO) service within Bluemix if one has not already been created:

    $ cf create-service SingleSignOn professional pipes-sso-service

### Deploying

To deploy manually to Bluemix, simply:

    $ git clone https://github.com/ibm-watson-data-lab/simple-data-pipe.git
    $ cd simple-data-pipe
    $ cf push

 > The Simple Data Pipe comes with a couple of data source connectors pre-installed. You can deploy additional connectors or build your own. [Visit Connector Central](https://developer.ibm.com/clouddataservices/simple-data-pipe-connectors/) to learn more.

**Note:** You may notice that Bluemix assigns a URL to your application containing a random word. This is defined in the `manifest.yml` file where the `random-route` key set to the value of `true`. This ensures that multiple people deploying this application to Bluemix do not run into naming collisions. To specify your own route, remove the `random-route` line from the `manifest.yml` file and add a `host` key with the unique value you would like to use for the host name.

#### License 

Copyright [2015-2016] [IBM Cloud Data Services]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
