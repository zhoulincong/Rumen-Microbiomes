# Knowledge Graph Construction and Visualization

## Introduction
**Knowledge Graph Construction and Visualization** demonstrates how to build a knowledge graph using **Neo4j Desktop**. You can replicate my knowledge graph by importing the provided dump file, or you can build a similar graph structure on your own.

## Project Structure


├── dump/                # Contains the Neo4j database dump files
├── full_graph.dump      # Full graph data for entire knowledge graph
├── filtered_graph.txt   # Cypher queries to create the filtered graph (focused on EC)
├── an.csv               # Data file for EC-related nodes
├── wu.csv               # Data file for Wuling-related nodes
├── README.md            # Project documentation
└── LICENSE              # Project license

## Prerequisites
Before getting started, ensure that the following tools and dependencies are installed:

1. **Neo4j Desktop** - Used for building and managing the knowledge graph database. You can download it from [here](https://neo4j.com/download/).

2. **DBMS Version Requirement**: When creating your project, make sure the **Neo4j DBMS version is >= 5.20.0**. Older versions may not be compatible with the provided dump file or may encounter issues during import.

## How to Replicate My Graph

### 1. Install Neo4j Desktop
If you have not yet installed **Neo4j Desktop**, you can download it from the official website and follow the installation guide.

### 2. Create a New Project and Import Data

#### To Replicate the Full Graph:
1. Open **Neo4j Desktop** and create a new project.
2. Inside the project, create a new database.
3. On the database management page, click the **"Restore"** button.
4. Select the `full_graph.dump` file from the `dump/` folder to restore the full knowledge graph.
5. Once the import is complete, start the database to view the entire graph.

#### To Focus on EC-related Nodes:
If you want to focus on a filtered version of the graph (specifically focusing on `EC` related data), follow these steps:
1. Open **Neo4j Desktop** and create a new project.
2. Inside the project, create a new database.
3. Import the two CSV files: `an.csv` and `wu.csv` by going to the **"Import"** section.
   - `an.csv`: Contains data related to EC nodes.
   - `wu.csv`: Contains data related to Wuling nodes.
4. Once the CSV files are imported, open the **Neo4j Browser** and run the Cypher queries provided in the `filtered_graph.txt` file to build the graph focusing on the `EC` nodes.

### 3. Start the Database
Start your database instance and ensure it connects successfully. You can interact with it via the **Neo4j Browser** at the default address: `http://localhost:7474`.

## Cypher Query Examples
In the **Neo4j Browser**, you can use **Cypher** language to query the graph. Here are some simple query examples:

### Retrieve All Nodes
```cypher
MATCH (n) RETURN n LIMIT 25;

This query will return the first 25 nodes in the graph.
Retrieve Specific Nodes

Assuming there is a node label called EC, you can use the following query to retrieve all EC nodes:
MATCH (n:EC) RETURN n LIMIT 10;

Retrieve Relationships Between Nodes

If you want to query the relationships between two nodes, for example, find all relationships where SpeciesName nodes are related to EC nodes via the belongto relationship, you can use the following query:
MATCH p=()-[r:belongto]->() RETURN p LIMIT 25;

Graph Structure Overview

In this project, the knowledge graph I built consists of the following main elements:
Node Types: Includes Angus (cattle), Wuling (cattle), SpeciesName, EC.
Relationship Types: Includes HAS (cattle-SpeciesName relationship), belongto (SpeciesName-EC relationship).

The specific design of nodes and relationships can be expanded or modified based on your actual needs. You can explore and analyze the graph structure further in the Neo4j Browser.
Contributing

If you have any suggestions for improvements or encounter issues, feel free to submit Issues or Pull Requests. We welcome contributions in any form!
License

This project is licensed under the MIT License. Feel free to use and modify it as you wish.
