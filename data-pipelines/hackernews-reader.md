# Hackernews Reader (ingest pipeline)

Hackernews Reader uses [http-source] to build an XML reader that ingests hackernews articles, converts them to `json`, divides them into records, and publishes each record to a topic.

## Objective

Show an example on how to query XML RSS feeds and convert each article into an individual JSON event for downstream processing.

## Prerequsites

* [Fluvio CLI] running locally
* Account on [InfinyOn Cloud]

## Step-by-Step

1. [Create http-source configuration file](#create-http-source-configuration-file)
2. [Download smartmodules](#download-startmodules)
3. [Start Connector](#start-connector)
4. [Check Results](#check-results)

### Create http-source configuration file

Create an HTTP source connector configuration file called `hackernews.yaml` :

```yaml
apiVersion: 0.1.0
meta:
  version: 0.1.0
  name: hackernews 
  type: http-source
  topic: hackernews
http:
  method: GET
  endpoint: 'https://hnrss.org/newest'
  interval: 600s
transforms:
  - uses: infinyon-labs/rss-json@0.1.0
  - uses: infinyon/jolt@0.2.0
    with:
      spec:
      - operation: shift
        spec:
          items: ""
  - uses: infinyon-labs/array-map-json@0.1.0
```

### Download startmodules

Download the smartmodules used by the connectors to your cluster:

```bash
fluvio hub download infinyon-labs/rss-json@0.1.0
fluvio hub download infinyon/jolt@0.2.0
fluvio hub download infinyon-labs/array-map-json@0.1.0
```

### Start Connector

```bash
fluvio cloud connector create -c hackernews.yaml
```

### Check Results

Connector logs:

```bash
fluvio cloud connector log hackernews
```

Records produced:

```bash
fluvio consume hackernews -T 10
```

### References

* [How to Stream and Transform Data from Hacker News RSS Feed (YouTube Video)]


---
[Fluvio CLI]: https://www.fluvio.io/download
[InfinyOn Cloud]: https://infinyon.cloud/signup
[http-source]: https://github.com/infinyon/http-source-connector
[rss-json]: https://github.com/infinyon/labs-rss-json-sm
[jolt]: https://github.com/infinyon/fluvio-jolt
[array-map-json]: https://github.com/infinyon/labs-array-map-json-sm
[How to Stream and Transform Data from Hacker News RSS Feed (YouTube Video)]: https://www.youtube.com/watch?v=raV5q6paAPM&t=1s&ab_channel=InfinyOn