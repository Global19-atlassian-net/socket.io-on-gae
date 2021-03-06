# socket.io on Google App Engine using node.js

Contents below are of [websockets sample](https://goo.gl/l3OePg) in GAE and setup is also applicable to socket.io.
This sample demonstrates how to use WebSockets on
[Google App Engine Managed VMs](https://cloud.google.com/appengine) with Node.js.

__Note:__ Secure WebSockets are currently not supported by Managed VMs.
WebSockets will only work if you load your page over HTTP (not HTTPS).

To use Secure WebSockets now, you can launch a VM on Google Compute Engine using
a custom image where you have added SSL support for WebSockets.

Refer to the [appengine/README.md](../README.md) file for instructions on
running and deploying.

## Setup

Before you can run or deploy the sample, you will need to create a new firewall
rule to allow traffic on port 65080. This port will be used for websocket
connections. You can do this with the
[Google Cloud SDK](https://cloud.google.com/sdk) with the following command:

    gcloud compute firewall-rules create default-allow-websockets \
      --allow tcp:65080 \
      --target-tags websocket \
      --description "Allow websocket traffic on port 65080"
