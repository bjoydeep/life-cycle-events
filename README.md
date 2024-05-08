# Event API Specifications
These are events generated on the Kafka Topics by ACM.   The evets generated by the Common Inventory infrastructure will be defined in due course (they will be distinct and different from these)

## Topics
The following Kafka topics are used
- spec
- event
- status

_if we change the kafka topic names: example change `spec` to `acm-spec` does that break backward compatibility or cause issues during upgrade_

## Event Structure

The events are formatted as per Cloud Event Specifications. Therefore the message envelopes are common as specified by the Cloud Event Specs. The `data` field which carries the real message payload is described in the sections below.

|Field|datatype|Cloud Event Envelope|Event Payload|Note|
|----|----|----|----|----|
|id|string|Yes||kube event-id; for non-kube, it needs to be generated|
|source|string|Yes||ACM or ACS etc. Do we need a list of sources? Does it need to be namespaced (acm.hub1 etc)|
|spec_version|string|Yes||Is this the Cloud Event version?|
|type|string|Yes||one of the above. Do we need a list of types?|
|date-time||||Based on GMT; |
|data|any||Yes|This is the real payload and we will describe this payload under each subsection below|
|kafkamessagekey||||Being added by GH Agent for ease of consumption|
|kafkapartition||||Being added by GH Agent for ease of consumption|
|extversion||||Being added by GH Agent for ease of consumption|,
|kafkaoffset||||Being added by GH Agent for ease of consumption|
|kafkatopic||||Being added by GH Agent for ease of consumption|

### data field for each topic

#### Topic spec

#### Topic status

#### Topic event


# -----------IGNORE BELOW----


### Events from Cluster

|Number|Type of Event|Inventory Consumer|Cluster Management Tool|
|----:|:-----|------:|-------:|
|1|cluster creation about to start|-|Yes|
|2|cluster creation complete|-|Yes|
|3|cluster creation error|-|Yes|
|4|cluster import started|-|Yes|
|5|cluster import complete|-|Yes|
|6|cluster import error|-|Yes|
|7|cluster under management|Yes|Yes|
|8|cluster capacity change|Yes|Yes|
|9|cluster version updated|Yes|Yes|


### Event Structure

|Field|datatype|Cloud Event Envelope|Event Payload|Note|
|----|----|----|----|----|
|id|string|Yes||kube event-id; for non-kube, it needs to be generated|
|source|string|Yes||ACM or ACS etc. Do we need a list of sources? Does it need to be namespaced (acm.hub1 etc)|
|spec_version|string|Yes||event version or ?|
|type|string|Yes||one of the above. Do we need a list of types?|
|date-time||||Based on GMT|
|DATA|||||
|cluster-id|||Yes|OpenShift Cluster-id. For *KS? What happens before cluster is created. This the object that emits the event.|
|message|||Yes|Event message|
|datetime|||Yes||

spec, status, labels, annotations, kind, metadata

Being added by GH agent to help in consuming:

- "kafkamessagekey": "kind-hub1",
- "kafkapartition": "0",
- "extversion": "0.1",
- "kafkaoffset": "1183",
- "kafkatopic": "status.kind-hub1"





### Events from Policy



