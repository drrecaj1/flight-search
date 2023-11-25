# Technical Report: Flight-search Engine

## Introduction
Provide a brief introduction to your project, including its purpose, objectives, and scope. Mention the key goals and what you aimed to achieve with this project.

## Strategic Decisions
### Algorithm : 
The breadth-first search (BFS) algorithm, a well-known method in computer science for browsing or exploring tree and graph data structures, powers the aircraft search engine. Starting with the departure city, or any random node in a network, it initially investigates its neighbors before proceeding to the next level of nodes. This algorithm views every city as a node and every flight path as an edge in a graph related to the flight search engine. The BFS algorithm investigates all direct flights from the origin city, then proceeds to the destinations of these flights to investigate further connections. The method covers every path from the origin to the destination by repeating this multiple times, despite the limitations of budget and maximum stops. Finding the shortest path in terms of connections is one of the main functions of the BFS algorithm in this application, which is essential for users with limited flexibility in their trip plans, such families or tour groups. Furthermore, by modifying the search parameters to account for flight expenses, the algorithm may accommodate budgetary limitations, guaranteeing that the suggested routes are accessible to the travelers

