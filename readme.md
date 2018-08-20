# docker-elasticsearch-curator: updated for Curator v5.5.4

This Docker container is used to clear ElasticSearch indices.

## Configuration

The index filtering can be configured in `curator_actions.yml`. At the moment it is configured to clear ES results matching indice `apm-6.2.4-transaction-` older than 7 days.

`curator.yml` is used to configure the ElasticSearch instance hostname and port.

## Deployment

It can be run as follows:

	docker run -d -e INTERVAL_IN_MINUTES=60 -e OLDER_THAN_IN_DAYS="10" --link es1:elasticsearch visity/elasticsearch-curator
	
where **es1** is the name of the elasticsearch container and

* **INTERVAL\_IN\_MINUTES**: The amount of time between two curator runs
* **OLDER\_THAN\_IN\_DAYS**: Indicates all logs with a date exceeding this age can be deleted.

