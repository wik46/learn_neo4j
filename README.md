# Learn_Neo4j
* Description: This is a repository created while learning how to use a graph data base. In particular learning Neo4j

## Overview:
* Getting a database up and runnnig.
* Importing data into the database.
* Introductoin to Cypher. (graph database query language)
* Additonal resources.


## Getting a database up and runnnig.
We will start our Neo4j instace inside a docker container.
```
docker run \
    --name my_db \
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
* Take note of the neo4j/ import directory. This is where you will store any datafile that you want to import using LOAD CSV.

## Importing data into the database.
* There are many ways to import data into Neo4j. We will consider 2
  * Using LOAD CSV provided by Cypher.
      Download a dataset that you would like to use. In my case I used the <a href="http://nflsavant.com/about.php">NFL Players dataset.</a>
  * Using language specific drivers. (in this case Python's community driver package called py2neo)
    
## Introduction to Cypher. (graph database query language)
## Additonal resources.
