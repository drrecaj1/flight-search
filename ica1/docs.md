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

![BFS](https://github.com/drrecaj1/flight-search/assets/122489106/2ad4bceb-732c-4dfe-832b-cacec5c1e30e)



## Implementation Details
Our Clojure-based flight search engine was implemented using a number of crucial processes to convert the unstructured flight data into a searchable format. Then, the Breadth-First Search (BFS) method was applied to this data to identify the best flight paths. 

### Data Parsing and Structure

- **Initial Data Processing:** The flight data has to be parsed into a more readable format because it was originally given as a long string. The strong string and collection manipulation features in Clojure were used to achieve this. In this phase, the create-flight-list function played a crucial role by segmenting the string into distinct flight entries, each of which included the cost, the departure and destination cities, and other details.
- **Graph Creation:** The create-graph function was used to convert this list of flights into a structure resembling a graph in the next stage. This program essentially created a network of nodes (cities) and edges (flight routes) that appropriately reflected the available flight pathways by mapping each city to its potential destinations and the associated expenses.
- **Handling Return Flights:** One noteworthy feature of our solution was that all flights had to be treated as return flights, which doubled the number of possible routes. This was fixed during the data processing phase, when a matching return flight was added to the flight list for every direct flight entry, guaranteeing a thorough depiction of all feasible routes.
- **Generating User-Specific Travel Options:** The incorporation of the prepare-travel-plan function to our implementation was noteworthy in our project. This function took center stage when the graph was constructed and the possible paths were identified. It generated travel itineraries based on user-specific parameters, including the kind of passenger (family or group), budgetary restrictions, and the maximum number of stops, by using the organized flight network. The prepare-travel-plan function was able to customize the search results by incorporating the user inputs, offering solutions that were not only practical but also in line with the user's own travel requirements and tastes.

### Application of BFS Algorithm

- **Route Finding:** Our flight search engine's find-routes function, which used the BFS algorithm, served as its main feature. This function examined every possible path from the departing city to the destination using the graph structure and user-specified parameters like budget and the maximum number of stops.
- **Algorithm Customization:** In order to guarantee that the solutions offered were within the user's budget, BFS was modified to not only determine the shortest path in terms of stops but also to select routes based on the overall cost. Serving the varied demands of our target audience, which included families and tour groups with various financial restraints, required this modification.

### Backend Focus
- **User Interaction:** The principal role of our application included a straightforward console-based interface that allowed for user interaction, even if the application's primary concentration was on backend processing. To obtain customized travel schedules, users may enter their starting and ending locations as well as the type of passenger they are traveling with (family or group).
- **No Frontend Interface:** The project refrained from creating a frontend interface in order to keep things simple and focus on algorithmic performance. Backend logic received all of the attention, which made the flight search engine reliable, effective, and precise in its route recommendations.

## Challenges and Solutions



## Results and Discussion



