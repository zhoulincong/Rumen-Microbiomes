Knowledge Graph Construction and Visualization

This project demonstrates how to build a knowledge graph using Neo4j Desktop and visualize it on a webpage using Neovis.js. You can replicate my knowledge graph by importing the provided dump file, or build a similar graph structure on your own.
Project Structure

├── dump/                # Contains the Neo4j database dump files
├── index.html           # Web visualization file
├── README.md            # Project documentation
└── LICENSE              # Project license

Prerequisites

Before getting started, you need to ensure that the following tools and dependencies are installed:
Neo4j Desktop - Used for building and managing the knowledge graph database. You can download it from here.
Neovis.js - Used to visualize Neo4j data as a graph. The Neovis.js library is already integrated into the index.html file.

How to Replicate My Graph

1. Install Neo4j Desktop

If you have not yet installed Neo4j Desktop, you can download it from the official website and follow the installation guide.
2. Import Data

I have exported the graph data as a Neo4j database .dump file, located in the dump/ folder. Follow these steps to import the data:
Open Neo4j Desktop and create a new database.
On the database management page, click the "Restore" button.
Select the .dump file from the dump/ folder to restore the database.
Once the import is complete, start the database.

3. Start the Database

Start your database instance and ensure it connects successfully. You can interact with it via the Neo4j Browser at the default address http://localhost:7474.
Web Visualization

I use Neovis.js to visualize the graph structure from the database as a graph on a webpage. To view my graph visualization:
Create a new .html file, write the HTML code for visualization (the HTML code is already provided), and then open this .html file directly in your browser to see the visualization.
Cypher Query Examples

In the Neo4j Browser, you can use Cypher language to query the graph. Here are some simple query examples:
Retrieve All Nodes

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

This translation keeps the structure and tone professional and ensures the instructions and information are clearly communicated in English. Let me know if you need any further modifications!
