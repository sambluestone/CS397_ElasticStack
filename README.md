# ELKB (Elasticsearch + Logstash + Kibana + Beats) 6.4.0 with Docker

Add the hosts to your machine. Edit the folllowing files depending on your OS:

- Mac: /private/etc/hosts
- Windows: C:\Windows\System32\drivers\etc\hosts
- Linux: /etc/hosts

Then, add the following line to the hosts file.

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
