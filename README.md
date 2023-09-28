# InfinyOn Labs Projects

InfinyOn Labs is a collection of projects that helps the community accelerate the pace of innovation through experimentation. The projects here use various components, some of which may be custom connectors and smartmodules that InfinyOn does not guarantee to run in production environments.

## Community Engagement

Smartmodules and Connectors referenced in this repo must have two components:

* **binary** published in `InfinyOn Hub`
* **public repo** in `github`

As a member of the Fluvio community, you are encouraged to contribute to these projects or submit new ones. 

## Voting

The InfinyOn team is committed to working with the community and turning the most popular `labs` projects into `certified` modules. Certified modules are integrated into the InfinyOn CI/CD pipeline and are safe for production workloads.

[Vote Here] if you want you want a project to be promoted to `certified`, and we'll prioritize accordingly.

## Data Pipelines

Configuration files that provision data pipelines using a combination of connectors and smartmodules. The projects are defined by configuration file operated via DSL, and should not require coding.

| Pipeline Project    | Description                                 |
| ------------------- | ------------------------------------------- |
| [hackernews-reader] | Reads Hackernews XML feed and converts each article into a JON record |
| [webhook-to-slack]  | Convert events receives from the InfinyOn webhook API and notify on Slack |
| [github-to-slack]   | Periodically checks a github repo for changes in starts/forks, and notifies on Slack |
| [github-to-discord] | Checks a github repo for starts/forks, and notifies on Discord |

## SmartModules

Smartmodule projects used to build the `labs` projects. You may clone, and enhance:

| Smartmodule Project           | Record Type | Description                           |
| ----------------------------- | ----------- | ------------------------------------- |
| [labs-rss-json-sm]            | xml / json  | Parses RSS XML input into JSON format |
| [labs-json-formatter-sm]      | json        | Generated a formatted string from JSON values |
| [labs-key-gen-json-sm]        | json        | Generates a unique key (digest) from JSON values |
| [labs-array-map-json-sm]      | json        | Splits an JSON array into individual records |
| [labs-regex-map-json-sm]      | json        | Applies Regex transformations on JSON values |
| [labs-stars-forks-changes-sm] | json        | Detects changes in github stars & forks, and generates an emoji string |
| [labs-regex-map-sm]           | text        | Applies Regex transformations on arbitrary text |

For additional examples, checkout [fluvio/smartmodules].

## Connectors

Connectors in development as incubated labs projects:

| Connector Project            | Status       | Description                           |
| ---------------------------- | ------------ | ------------------------------------- |
| [labs-redis-sink-connector]  | experimental | Fluvio to Redis                       |
| labs-s3-sink-connector       | roadmap      | Fluvio to S3                          |

Note, all certified connectors are available for use in labs projects:

| Connector Project            | Status       | Description                           |
| ---------------------------- | ------------ | ------------------------------------- |
| [http-source-connector]      | certified    | HTTP (POST/GET) to fluvio             |
| [http-sink-connector]        | certified    | fluvio to HTTP (POST)                 |
| [kafka-source-connector]     | certified    | Kafka to fluvio                       |
| [kafka-sink-connector]       | certified    | fluvio to Kafka                       |
| [mqtt-source-connector]      | certified    | mqtt to fluvio                        |
| [sql-sink-connector]         | certified    | fluvio to SQL                         |


Connector **status** definition:
* `roadmap` - requested by the community, 
* `experimental` - under development (compile and run on your own)
* `stable` - proven to work, but not yet certified (compile and run on your own)
* `certified` - certified and available on InfinyOn Cloud and local environments



[Vote Here]: https://docs.google.com/forms/d/1yK8k-7Udq2wteNw-ZJm8Q59pvpwqduzUexSSUmgsYzI/

[hackernews-reader]: data-pipelines/hackernews-reader.md
[github-to-discord]: data-pipelines/github-to-discord.md
[github-to-slack]: data-pipelines/github-to-slack.md
[webhook-to-slack]: data-pipelines/webhook-to-slack.md

[labs-rss-json-sm]: https://github.com/infinyon/labs-rss-json-sm
[labs-json-formatter-sm]: https://github.com/infinyon/labs-json-formatter-sm
[labs-key-gen-json-sm]: https://github.com/infinyon/labs-key-gen-json-sm
[labs-array-map-json-sm]: https://github.com/infinyon/labs-array-map-json-sm
[labs-regex-map-json-sm]: https://github.com/infinyon/labs-regex-map-json-sm
[labs-stars-forks-changes-sm]: https://github.com/infinyon/labs-stars-forks-changes-sm
[labs-regex-map-sm]: https://github.com/infinyon/labs-regex-map-sm

[labs-redis-sink-connector]: https://github.com/infinyon/labs-redis-sink-connector
[http-source-connector]: https://github.com/infinyon/http-source-connector
[http-sink-connector]: https://github.com/infinyon/http-sink-connector
[kafka-sink-connector]: https://github.com/infinyon/kafka-connector/tree/main/crates/kafka-sink
[kafka-source-connector]: https://github.com/infinyon/kafka-connector/tree/main/crates/kafka-source
[sql-sink-connector]: https://github.com/infinyon/sql-connector
[mqtt-source-connector]: https://github.com/infinyon/mqtt-connector

[fluvio/smartmodules]: https://github.com/infinyon/fluvio/tree/master/smartmodule/examples
