# docker_log_collect

This project provides a simple and efficient solution for sending Docker container logs to Elasticsearch and visualizaing them using Kibana. This is achieved thanks to Filebeat. We set up Elasticsearch and Kibana using Docker Compose to make Docker container logs to make the search easy through the Kibana interface. Filebeat is used to read logs and move them to Elasticsearch.

## Setup

1. Clone this repository
2. Ensure both Docker and Docker Compose are installed on your machine.
3. Run the command `docker-compose up` to start the Elasticsearch, Kibana and Filebeat services.
4. You can verify in the Docker application that 3 containers will be running. Note that Kibana will be accessible at `http://localhost:5601` after we started the services with Docker Compose.

## Troubleshooting

### FileBeat container not starting

If the Filebeat container fails to start, it could be due to insufficient file permissions for the filebeat.yml configuration file. In this case, you might need to modify the file permissions using the following `chmod` command:

```
chmod go-w ./config/filebeat.yml
```

## Additional Information

For additional information about the configuration, you can refer to the following article: [Sending Docker Logs to ElasticSearch and Kibana with FileBeat](https://www.sarulabs.com/post/5/2019-08-12/sending-docker-logs-to-elasticsearch-and-kibana-with-filebeat.html)