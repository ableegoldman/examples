![image](../images/confluent-logo-300-2.png)

# Overview

This demo showcases a AWS Kinesis -> Confluent Cloud -> Google Cloud Storage pipeline.

![image](images/topology.jpg)

Benefits:

* Span cloud providers and datacenters
* Leverage Kafka's rich ecosystem of a full event streaming platform
* Aggregate data in single source of truth
* Use power of KSQL


# Prerequisites

## Local

As with the other demos in this repo, you may run the entire demo end-to-end with `./start.sh`, and it runs on your local Confluent Platform install.  This requires the following:

* [Common demo prerequisites](https://github.com/confluentinc/examples#prerequisites)
* [Confluent Platform 5.2](https://www.confluent.io/download/)
* [An initialized Confluent Cloud cluster used for development only](https://confluent.cloud)
* Access to Kinesis S3
* Google GCS storage related requirements
  * `gsutils`: Cloud SDK https://cloud.google.com/sdk/
* AWS S3 storage related requirements
  * `aws cli`
  * AWS properly credentials configured on your host
* `jq`
* `curl`


# Run the demo

1. Configure the destination cloud storage and other demo parameters in the `config/demo.cfg` file. In particular, be sure to configure the `DESTINATION_STORAGE` parameter appropriately for Google GCS or AWS S3, and set the appropriate region.

2. Run the demo:

```bash
$ ./start.sh
```

3. View all the Kinesis, Kafka, and cloud storage data after running the demo:

```bash
$ ./read-data.sh
```

4. Stop the demo and clean up:

```bash
$ ./stop.sh
```