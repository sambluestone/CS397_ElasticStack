# Elasticstack - CS397: Tool Web Page

## What is Elasticstack and why does it matter?

#### Brief Overview:

**Elasticstack** is the world's most popular log management platform, developed and maintained by [Elastic](https://www.elastic.co/). It is originally a collection of 3 open-source projects, called ELK Stack, until the addition of Beats and other plugins. In short, it helps to aggregate, process, store and analyze logging data from multiple sources to ensure an app's availability, performance and security.

#### Goal and Motivation:

- **Motivation**: Logs have always existed, but their underlying architecture of environments have evolved to become more complex with TB of logs generated daily. This gives rises to the need for a centralized log management and analytics solution.
- **Goal**: Provide a holistic evaluation of apps' performance and security in real time.

## Components of Elasticstack

![a flow chart that shows the relationship between beat, buffering plug ins, logstach, elastic search, and kibana](https://dytvr9ot2sszz.cloudfront.net/wp-content/uploads/2021/04/Group-1207.jpg)

### Beats

- This component sits closest to your application.
- A collection of lightweight open source data shippers that are installed on your servers to acquire data and then feed it to Elasticsearch
- You can create your own custom beat depending on the type of data you have
- You can use Beats to send data to Elasticsearch directly, or you can send it to Logstash first for enhanced filtering and data processing.
  - For this reason, there are lots of beats available

**Features**: Six official Beats from Elastic

- Filebeat: Reads files from your system
- Metricbeat: Collect metrics from servers and systems
- Packetbeat: Network packet analyzer
- Heartbeat: Lightweight uptime monitoring
- Winlogbeat: Windows event logs
- Auditbeat: Similar to Winlog but for Linux platforms

Resources

- https://www.objectrocket.com/resource/what-are-elasticsearch-beats/
- https://www.elastic.co/beats/
- Downloads: https://www.elastic.co/downloads/beats/
- Documentation: https://www.elastic.co/guide/en/beats/libbeat/current/index.html

### Logstash

- A data processing pipeline that ingests data from multiple sources, transforms it, and sends it to a specific “stash”

**Features**

- Ability to parse and identify relevant fields
- Anonymize PII (personal identifiable information) that appears in your data.
- Grab data from various cloud services (e.g. your AWS infrastructure) or Beats
- Outputse
  - AWS S3 bucket (cloud storage service)
  - AWS Cloudwatch (metric collection service)
  - HTTP endpoint
  - Elasticsearch
  - CSV file
  - Many others

Image below from: https://www.elastic.co/guide/en/beats/libbeat/current/beats-reference.html
![](https://i.imgur.com/YPRhTds.png)

### Elasticsearch

- A distributed, RESTful search and analytics engine capable of addressing a growing number of use cases. As the heart of the Elasticstack, it centrally stores your data for lightning fast search, fine‑tuned relevancy, and powerful analytics that scale with ease.
- Supported programming languages:
  - Curl
  - C# (.NET)
  - Go
  - Java
  - JavaScript (Node.js)
  - PHP
  - Perl
  - Python
  - Ruby
  - SQL

**Usage**

- Replaces tools like grep that are used to search
- Faster searches

**Features**

- Uses the REST API instead of SQL
- Types of searchable data:
  - Structure
  - Unstructured
  - Geo
  - Metric
- Everything is indexed to give rapid results
- Data returned as a JSON
- Handles typos
- Aggregations: summarize data into metrics, statistics, or other analytics to allow you to see the bigger picture of your data
  - Sample questions:
    - What’s the average load time for my website?
    - Who are my most valuable customers based on transaction volume?
    - What would be considered a large file on my network?
    - How many products are in each product category?
    - Elasticsearch organizes aggregations into three categories:
  - Sample aggregations
    - Metric aggregations: calculate metrics, such as a sum or average, from field values.
    - Bucket aggregations: group documents into buckets or bins based on field values, ranges, or other criteria
    - Pipeline aggregations: take input from other aggregations instead of documents or fields

**Possible Use Cases**

- Add a search box to an app or website
- Store and analyze logs, metrics, and security event data
- Use machine learning to automatically model the behavior of your data in real time
- Automate business workflows using Elasticsearch as a storage engine
- Manage, integrate, and analyze spatial information using Elasticsearch as a geographic information system (GIS)
- Store and process genetic data using Elasticsearch as a bioinformatics research tool

### Kibana

- A browser-based user interface used to search, analyze & visualize data stored in Elasticsearch indices and is built on top of Elasticsearch
- Run on `node.js` , can be installed on Linux, Windows, Mac, repositories or Docker

#### Functionality:

**Searching**: KQL (Kibana Querying Language) to search data (Lucene before)

- Common search types:
  - Free text searches: search a specific string
  - Field-level searches: search a string within a specific field
  - Logical statements: combine searches into a logical statement
  - Proximity searches: search terms within a specific character proximity
- Autocomplete capability

**Filtering**: to assist in searches → allow easier filtering of data displayed in the main view

**Visualizations:**

- Basic charts (Area, Heat map, Horizontal bar, Line, Pie, Vertical bar)
- Data (Data table, Gauge, Goal, Metric)
- Maps (Coordinate Map, Region Map)
- Time series (Timelion, Visual Builder)
- Other (Controls, Markdown, Tag Cloud)

**Dashboards:** 1 comprehensive visualization which contains a collection of visualizations

**Pages:** dedicated pages for various monitoring features

- Canvas
- Maps
- Infrastructure
- Logs
- APM (App performance monitoring)
- Uptime
- Stack monitoring

**Elasticsearch index**: searches, visualizations, dashboards in Kibana are called objects, which are stored in a dedicated Elasticsearch index (`.kibana`) for debugging, sharing, repeated usage & backup. The index contains:

- saved index patterns
- saved searches
- saved visualizations
- saved dashboards

## Plugins and add ons

**Buffers**: logs can surge and overwhelm the stack so buffers are used to control the flow of data to the stack so buffers act as the "brokers the data flow and queues it"

- the most popular buffer plug in is Apache Kafka
- really useful becuase it proctects your system from overloads if you drop a new update or a new website

## Resources and Links

- Official documentation and link to tools:
  - [Elastic Stack and Product Documentation](https://www.elastic.co/guide/index.html)
  - [Installation Guide](https://www.elastic.co/guide/en/elastic-stack-get-started/current/get-started-elastic-stack.html)
  - [Beats](https://www.elastic.co/beats/)
  - [Logtash](https://www.elastic.co/logstash/)
  - [Elasticsearch](https://www.elastic.co/elasticsearch/)
  - [Kibana](https://www.elastic.co/kibana/)
  - [Offical blog posts and news](https://www.elastic.co/blog/)
  - [Interactive demo](https://demo.elastic.co/)
- Good documentation links and tutorials:
  - Quick Start Tutorials
    - [Elastic Search](https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started.html)
    - [Kibana](https://www.elastic.co/guide/en/kibana/current/get-started.html)
    - [Logstash](https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html)
  - [A brief introduction to Elastick Stack](https://hackernoon.com/elastic-stack-a-brief-introduction-794bc7ff7d4f)
  - [The Complete Guide to ELK STACK](https://logz.io/learn/complete-guide-elk-stack/#installing-elk)
  - [Python tutorial](https://www.freecodecamp.org/news/how-to-use-elasticsearch-logstash-and-kibana-to-visualise-logs-in-python-in-realtime-acaab281c9de/)
- Alternatives:
  - [Comparably](https://www.comparably.com/companies/366173/competitors)
  - [Splunk versus Elastic Stack](https://devops.com/splunk-elk-stack-side-side-comparison/)

## [Presentation Link](https://docs.google.com/presentation/d/e/2PACX-1vRK9nqjKt_cyc9jJUBiQne398hHJSL7I3k33DLeTv3nyzQ290kVKKdMz4nztqaWAKfHpDG_zeOD2nBC/pub?start=false&loop=false&delayms=3000)

<figure class="video_container">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRK9nqjKt_cyc9jJUBiQne398hHJSL7I3k33DLeTv3nyzQ290kVKKdMz4nztqaWAKfHpDG_zeOD2nBC/embed?start=false&loop=false&delayms=10000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

## Other Notes and Information

- Since Kibana is built on top of Elasticsearch, you have to download both for Kibana to work
- Installing all components on your local machine is resources- and time-intensive, so you might want to use Docker to install them.

## Elastic Stack Demo (Filebeats + Logstash + Elastic Search + Kibana)

Demo forked from: https://github.com/ThiagoBarradas/logstash-beats-demo

See presenatation slides for screenshots from the demo.

### Usage Instructions

Add the hosts to your machine. Edit the folllowing files depending on your OS:

- Mac: /private/etc/hosts
- Windows: C:\Windows\System32\drivers\etc\hosts
- Linux: /etc/hosts

Then, add the following lines to the hosts file.

```
127.0.0.1    elasticsearch.local
127.0.0.1    kibana.local
```

[Install Docker](https://docs.docker.com/get-docker/) if you haven't already.

Run the stack:

```
docker-compose up -d
```

- User `elastic` and password `123change...`
- Elasticsearch: http://elasticsearch.local
- Kibana: http://kibana.local
- For logstash demo, see confs in `logstash/conf` dir
- CSV used to load data is in `logstash/csv` dir
- For elasticsearch configuration, see `elasticsearch.yml` in `elasticsearch/config` dir
- Search for test `http://elasticsearch.local/hits-*/_search`
- Search for test `http://elasticsearch.local/filebeat-*/_search`
