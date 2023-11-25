# Technical Report: Flight-search Engine

## Introduction
This project invovles developing a flight search engine with the goal to make trip planning easier for two different clients in the company we are working with : schedueled tours and families. One of the main points the travel agency mentioned was to prioritize more expensive tickets in order to maintain the profitability of travel agency operations and to create a engine that works effectively to identify flights within financial and connection limits. The project's scope includes developing an algorithm that could meet the demands of the agency, and choosing an appropriate technological stack. Additionally , the user-journey of the client has to be excellent for the clients and the output of the engine has to be in a format that the user easily understands. These are the tasks that we have to work on during the creation of this engine. 


## Strategic Decisions
### Choices and Options Considered 
- **Technology Stack:** It was required that the project be developed in Clojure, a functional programming language famous for its immutable data structures and effective data management. Even though the language we would use was set, we nevertheless looked at other useful programs and libraries that would work well with Clojure, especially for managing flight data and creating search engines. The project's focus on lightweight and simple-to-integrate web frameworks and databases stemmed from its origins as an engine rather than a fully functional application.
- **Algorithmic Approach:** We evaluated two main algorithmic approaches: Depth-First Search (DFS) and Breadth-First Search (BFS), given the project's principal need of finding optimal flying routes. Both algorithms are essential to graph theory and are used to traverse or explore tree and graph structures. They differ in terms of complexity and search approach.
- **Tools and Libraries:**






## Algorithm : 
The breadth-first search (BFS) algorithm, a well-known method in computer science for browsing or exploring tree and graph data structures, powers the aircraft search engine. Starting with the departure city, or any random node in a network, it initially investigates its neighbors before proceeding to the next level of nodes. This algorithm views every city as a node and every flight path as an edge in a graph related to the flight search engine. The BFS algorithm investigates all direct flights from the origin city, then proceeds to the destinations of these flights to investigate further connections. The method covers every path from the origin to the destination by repeating this multiple times, despite the limitations of budget and maximum stops. Finding the shortest path in terms of connections is one of the main functions of the BFS algorithm in this application, which is essential for users with limited flexibility in their trip plans, such families or tour groups. Furthermore, by modifying the search parameters to account for flight expenses, the algorithm may accommodate budgetary limitations, guaranteeing that the suggested routes are accessible to the travelers

