<h1> Learn_Neo4j </h1>
* Description: This is a repository created while learning how to use a graph data base. In particular learning Neo4j

## Overview:
* Getting a database up and runnnig.
* Importing data into the database.
* Introductoin to Cypher. (graph database query language)
* Additonal resources.


## Getting a database up and runnnig.
We will start our Neo4j instace inside a docker container. You will need to <a href="https://docs.docker.com/get-docker/">install docker</a> of you don't have it installed.
```
docker run \
    --name learn_neo4j_db \
    -p7474:7474 -p7687:7687 \
    -d \
    -v $HOME/neo4j/data:/data \
    -v $HOME/neo4j/logs:/logs \
    -v $HOME/neo4j/import:/var/lib/neo4j/import \
    -v $HOME/neo4j/plugins:/plugins \
    --env NEO4J_AUTH=neo4j/your_own_password \
    neo4j:latest
```
* This will start a docker container running in the background.
* It will create a neo4j directory inside your home directory. 
* If you previously created a database, it will use the data from the neo4j diretory and continue from the older graph.
* Take note of the neo4j/ import directory. This is where you will store any datafile that you want to import using LOAD CSV.
* Also, all the data that you stored in the database will be stored inside the neo4j directory. This enables the user to restart the
    db and continue with the same database, as well as share the database.
* After starting the open a brower window and search the following.
```
    your_local_ip_address:7474
```
username: neo4j
password: your_own_password


## Importing data into the database.
* There are many ways to import data into Neo4j. We will consider 2
  * Using LOAD CSV provided by Cypher.
      Download a dataset that you would like to use. In my case I used the <a href="http://nflsavant.com/about.php">NFL Players dataset.</a>
  * Using language specific drivers. (in this case Python's community driver package called py2neo)
    
## Introduction to Cypher. (graph database query language)
## Additonal resources.
