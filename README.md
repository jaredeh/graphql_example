# graphql_example

We have two goals.

First, we want a bare bones example of best practices for using GraphQL in a React frontend, preferably using a well supported library.
Features:
* Periodically (1s) update CPU utilization from backend.
* Send a user supplied text message to backend.

Second, we want a GraphQL server that can respond to the frontend.  Implementation can be TypeScript, rust, or possibly python with justification. Backend should return to frontend data read from an influxdb filled by telegraf returning the metrics defined by the following telegraf plugins.
* https://github.com/influxdata/telegraf/tree/master/plugins/inputs/system
* https://github.com/influxdata/telegraf/tree/master/plugins/inputs/mem
* https://github.com/influxdata/telegraf/tree/master/plugins/inputs/nvidia_smi
  * If you do not have the ability to gather the nvidia_smi status at least include the metrics in the graphql schema and gracefully inform the frontend the nvidia_smi isn't working or just return 0/'' for all the fields.


Here we have included an example docker-compose.yml that will start a telegraf and influxdb instance.  This is the first version of what we would end up using to deploy the app you are developing the core of.
