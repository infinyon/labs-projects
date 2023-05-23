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

| <div style="width:175px">Pipeline Project<div> | Description |
| --- | --- |
| [hackernews-reader](data-pipelines/hackernews-reader.md) | Reads Hackernews XML feed and converts each article into a JON record |
| [github-to-discord](data-pipelines/github-to-discord.md) | Periodically checks a github repo for changes in starts/forks, and notifies on Discord |
| [github-to-slack](data-pipelines/github-to-slack.md) | Periodically checks github a repo for changes in starts/forks, and notifies on Slack |

## SmartModules

Smartmodule projects used to build the `labs` projects. You may clone, and enhance:

| <div style="width:225px">Smartmodule Project</div> | Record Type | Description |
| --- | --- | --- |
| [labs-rss-json-sm](https://github.com/infinyon/labs-rss-json-sm) | xml / json | Parses RSS XML input into JSON format |
| [labs-key-gen-json-sm](https://github.com/infinyon/labs-key-gen-json-sm) |json| Generates a unique key (digest) from JSON values |
| [labs-array-map-json-sm](https://github.com/infinyon/labs-array-map-json-sm) |json| Splits an JSON array into individual records |
| [labs-regex-map-json-sm](https://github.com/infinyon/labs-regex-map-json-sm) |json| Applies Regex transformations on JSON values |
| [labs-stars-forks-changes-sm](https://github.com/infinyon/labs-stars-forks-changes-sm) |json| Detects changes in github stars & forks, and generates an emoji string |
| [labs-regex-map-sm](https://github.com/infinyon/labs-regex-map-sm) |text | Applies Regex transformations on arbitrary text |

## Connectors

Connector projects:

* redis-sink (in development)
* s3-sink (in development)


-----
[Vote Here]: https://docs.google.com/forms/d/1yK8k-7Udq2wteNw-ZJm8Q59pvpwqduzUexSSUmgsYzI/
