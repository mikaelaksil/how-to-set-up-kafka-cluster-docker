# How to setup Kafka cluster using Docker

If you don't have docker already installed, download it from docker's website. Make sure you select the correct Operating System:
[Install Docker Desktop on Windows](https://docs.docker.com/desktop/windows/install/)

## Download the Kafka cluster

After you have successfully downloaded docker on your pc, create a file and save the following [docker-compose file](https://github.com/bitnami/bitnami-docker-kafka/blob/master/docker-compose-cluster.yml) as 'docker-compose.yml'

Then open cmd on that file and run the following command to upload the kafka cluster on your docker:
 ```sh
   docker-compose up -d
   ```
After that you should make sure that docker has downloaded the correct Images (check Images tab) and that there is a kafka cluster composed of 4 containers ( the zookeeper and 3 kafka brokers, check Containers tab).

If everything went right, the servers should be running already. In case they exited check the logs by clicking in the server that have stopped working.

Everything is setup! Now it's time to create your first kafka topic.
Use the following command in the same cmd that you openned previously :
```sh
   docker exec kafka kafka-topics.sh \ --create \ --bootstrap-server localhost:9092 \ --replication-factor 1 \ --partitions 10 \ --topic test
   ```
Here are some other commands that may be useful:  

    
   

To check the running containers:
 ```sh
   docker ps
   ```
To shutdown the cluster use:
 ```sh
   docker-compose down
   ```


## Credit
For more information visit /bitnami/bitnami-docker-kafka documentation
[Github Link](https://github.com/bitnami/bitnami-docker-kafka)


