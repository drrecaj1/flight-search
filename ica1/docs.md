# Technical Report: Flight-search Engine

## Introduction
This project invovles developing a flight search engine with the goal to make trip planning easier for two different clients in the company we are working with : schedueled tours and families. One of the main points the travel agency mentioned was to prioritize more expensive tickets in order to maintain the profitability of travel agency operations and to create a engine that works effectively to identify flights within financial and connection limits. The project's scope includes developing an algorithm that could meet the demands of the agency, and choosing an appropriate technological stack. Additionally , the user-journey of the client has to be excellent for the clients and the output of the engine has to be in a format that the user easily understands. These are the tasks that we have to work on during the creation of this engine. 


## Strategic Decisions
### Choices and Options Considered 
- **Technology Stack:** It was required that the project be developed in Clojure, a functional programming language famous for its immutable data structures and effective data management. Even though the language we would use was set, we nevertheless looked at other useful programs and libraries that would work well with Clojure, especially for managing flight data and creating search engines. The project's focus on lightweight and simple-to-integrate web frameworks and databases stemmed from its origins as an engine rather than a fully functional application.
- **Algorithmic Approach:** We evaluated two main algorithmic approaches: Depth-First Search (DFS) and Breadth-First Search (BFS), given the project's principal need of finding optimal flying routes. Both algorithms are essential to graph theory and are used to traverse or explore tree and graph structures. They differ in terms of complexity and search approach.
- **Tools and Libraries:**



## Evaluation of Choices/Algorithm chosen
Although we had to use Clojure as the programming language for our aircraft search engine project, we were free to choose whatever algorithmic method we wanted. Because Breadth-First Search (BFS) is more appropriate for exploring aircraft networks than Depth-First Search (DFS), we chose it. Before moving on to the next level, BFS, a well-known computer science technique for navigating tree and graph structures, thoroughly investigates all of the immediate connections starting from the departing city. In the graph-like structure of our flight search engine, our method treats every city as a node and every flight path as an edge.

By putting BFS into place, we made sure that all flights from the origin were taken into account first, then flights from those destinations, systematically covering all possible itineraries within the limitations of the budget and the number of stops that could be made. The quickest routes in terms of connections are found using this method, which is very useful for our target users—tour groups and families, for example—who frequently have limited flexibility in their travel schedules. Furthermore, BFS's flexibility in responding to cost factors fits with our objective of offering routes that are economical and effective for our consumers.

Conversely, DFS by definition favors route exploration that is more focused on depth. This may result in the consideration of longer and less effective routes before more straightforward or cost-effective ones are discovered. This kind of behavior might compromise the effectiveness of our flight search engine, which seeks to provide quick and affordable travel options. After weighing these factors, BFS was determined to be the better option since it better matched the goals of our project and Clojure's functional advantages when it came to managing intricate data structures and algorithmic procedures.


## Implementation Details


