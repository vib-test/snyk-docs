# Components of Snyk Broker

The Broker client and server act together as a tunnel to your code, sending requests by proxy from [snyk.io](http://snyk.io/) to a Git repository, fetching the files needed for scanning, for example, manifest files, from monitored repositories, and fetching results using webhooks posted by the Git service. You will install the Broker client. The Broker server is provided by Snyk and does not require installation.

The Broker client runs within your internal network, keeping sensitive data such as Git tokens within the network perimeter. The tunnel allows for scanning using only requests on an approved data list. This narrows the access permissions to the absolute minimum required for Snyk to monitor a repository. For more information, see [Approved data list for Snyk Broker](connections-with-snyk-broker.md#approved-data-list-for-snyk-broker).

For information about components required for using Snyk Code Agent, Snyk Container Registry Agent, and Snyk Broker for Infrastructure as Code, see [Define your Broker deployment components](prepare-snyk-broker-for-deployment.md#define-your-broker-deployment-components).

The diagram that follows illustrates how the basic components operate.

* All data, both in transit and at rest, is encrypted.
* Communication between the Client and the Server is over a secure WebSocket connection.
* There is no need to open incoming ports since the communication is initiated outbound.
* After the connection is initiated, the WebSocket connection is bi-directional.

<figure><img src="../../.gitbook/assets/Snyk Broker diagram.png" alt="Snyk Broker WebSocket initiated by Client over HTTPS"><figcaption><p>Snyk Broker WebSocket initiated by Client over HTTPS</p></figcaption></figure>

For details about the connections between Snyk and the Broker Client and allowed requests, see [Connections with Snyk Broker](connections-with-snyk-broker.md).
