# Technical Report: Flight-search Engine

## Introduction
This project invovles developing a flight search engine with the goal to make trip planning easier for two different clients in the company we are working with : schedueled tours and families. One of the main points the travel agency mentioned was to prioritize more expensive tickets in order to maintain the profitability of travel agency operations and to create a engine that works effectively to identify flights within financial and connection limits. The project's scope includes developing an algorithm that could meet the demands of the agency, and choosing an appropriate technological stack. Additionally , the user-journey of the client has to be excellent for the clients and the output of the engine has to be in a format that the user easily understands. These are the tasks that we have to work on during the creation of this engine. 


## Strategic Decisions
### Choices and Options Considered 
- **Technology Stack:** It was required that the project be developed in Clojure, a functional programming language famous for its immutable data structures and effective data management. Even though the language we would use was set, we nevertheless looked at other useful programs and libraries that would work well with Clojure, especially for managing flight data and creating search engines. The project's focus on lightweight and simple-to-integrate web frameworks and databases stemmed from its origins as an engine rather than a fully functional application.
- **Algorithmic Approach:** We evaluated two main algorithmic approaches: Depth-First Search (DFS) and Breadth-First Search (BFS), given the project's principal need of finding optimal flying routes. Both algorithms are essential to graph theory and are used to traverse or explore tree and graph structures. They differ in terms of complexity and search approach.
- **Tools and Libraries:**



## Evaluation of Choices/Algorithm chosen
Although we had to use Clojure as the programming language for our aircraft search engine project, we were free to choose whatever algorithmic method we wanted. We choose Breadth-First Search (BFS) because is more appropriate for exploring aircraft networks than Depth-First Search (DFS). Before moving on to the next level, BFS, a well-known computer science technique for navigating tree and graph structures, thoroughly investigates all of the immediate connections starting from the departing city. In the graph-like structure of our flight search engine, our method treats every city as a node and every flight path as an edge.

By putting BFS into place, we made sure that all flights from the origin were taken into account first, then flights from those destinations, systematically covering all possible itineraries within the limitations of the budget and the number of stops that could be made. The quickest routes in terms of connections are found using this method, which is very useful for our target users (groups and families) who frequently have limited flexibility in their travel schedules. Furthermore, BFS's flexibility in responding to cost factors fits with our objective of offering routes that are economical and effective for our consumers.

Conversely, DFS by definition favors route exploration that is more focused on depth. The use of DFS in our code may result in the consideration of longer and less effective routes before more straightforward or cost-effective ones are discovered. This kind of behavior might compromise the effectiveness of our flight search engine, which seeks to provide quick and affordable travel options. After weighing these factors, BFS was determined to be the better option since it better matched the goals of our project and Clojure's functional advantages when it came to managing intricate data structures and algorithmic procedures.

![Your paragraph text](https://github.com/drrecaj1/flight-search/assets/122489106/a9942c78-63d0-4197-ba73-5a6f64b226a0)

Above is a picture we drew to explain how BFS works in comparison with DFS. While DFS traveres through the left subtrees first and then through the right ones , the BFS goes through level one of "children" nodes, then it moves on to the level of "grandchildren" nodes and so on. 

## Implementation Details
Our Clojure-based flight search engine was implemented using a number of crucial processes to convert the unstructured flight data into a searchable format. Then, the Breadth-First Search (BFS) method was applied to this data to identify the best flight paths. 

### Data Parsing and Structure

- **Initial Data Processing:** The flight data has to be parsed into a more readable format because it was originally given as a long string. The strong string and collection manipulation features in Clojure were used to achieve this. In this phase, the create-flight-list function played a crucial role by segmenting the string into distinct flight entries, each of which included the cost, the departure and destination cities, and other details. Doing this, we made it possible the creation of return flights so that we have more possibilities on roads for our clients. 
- **Graph Creation:** The create-graph function was used to convert this list of flights into a structure resembling a graph in the next stage. This program essentially created a network of nodes (cities) and edges (flight routes) that appropriately reflected the available flight pathways by mapping each city to its potential destinations and the associated expenses.
- **Handling Return Flights:** One noteworthy feature of our solution was that all flights had to be treated as return flights, which doubled the number of possible routes. This was fixed during the data processing phase, when a matching return flight was added to the flight list for every direct flight entry, guaranteeing a thorough depiction of all feasible routes.
- **Generating User-Specific Travel Options:** The incorporation of the prepare-travel-plan function to our implementation was noteworthy in our project. This function took center stage when the graph was constructed and the possible paths were identified. It generated travel itineraries based on user-specific parameters, including the kind of passenger (family or group), budgetary restrictions, and the maximum number of stops, by using the organized flight network. The prepare-travel-plan function was able to customize the search results by incorporating the user inputs, offering solutions that were not only practical but also in line with the user's own travel requirements and tastes. 

### Application of BFS Algorithm

- **Route Finding:** Our flight search engine's find-routes function, which used the BFS algorithm, served as its main feature. This function examined every possible path from the departing city to the destination using the graph structure and user-specified parameters like budget and the maximum number of stops.
- **Algorithm Customization:** In order to guarantee that the solutions offered were within the user's budget, BFS was modified to not only determine the shortest path in terms of stops but also to select routes based on the overall cost. Serving the varied demands of our target audience, which included families and tour groups with various financial restraints, required this modification.

### Backend Focus
- **User Interaction:** The principal role of our application included a straightforward console-based interface that allowed for user interaction, even if the application's primary concentration was on backend processing. To obtain customized travel schedules, users may enter their starting and ending locations as well as the type of passenger they are traveling with (family or group). After the engine prints out their travel plans with the options, they will have the option to restart the engine or to exit and quit the program. This is also made possible with the user input whether they press "restart" or "exit".
- **No Frontend Interface:** The project refrained from creating a frontend interface in order to keep things simple and focus on algorithmic performance. Backend logic received all of the attention, which made the flight search engine reliable, effective, and precise in its route recommendations.

### Time and Memory Complexity Analysis:
-**Time Complexity:** We can use Big O, Big Theta, and Big Omega notations to understand the time complexity of our implementation of the BFS algorithm.

-**Big O (Worst-Case Complexity):** When V and E are the numbers of vertices (cities) and edges (flight routes), respectively, the          worst-case time complexity of BFS is O(V + E). When the search must search the entire network to locate a route, as is often the         case in highly connected graphs, this complexity is observed when the algorithm has to traverse every vertex and edge in the graph.

 -**Big Theta (Average-Case Complexity):**  θ(V + E) is the average-case complexity, or Big Theta complexity, for BFS. The BFS method will carry out operations proportionate to the sum of the vertices and edges in the majority of realistic circumstances, particularly with flight networks that are moderately connected. In this case, the average distribution of nodes and edges is assumed, meaning that it is not always necessary for the search to cover every possible path.    

 -**Big Omega (Best-Case Complexity):** Big Omega represents the best-case complexity, which is Ω(V), where the algorithm finds the desired path without having to go over every edge. This could happen when the destination is located inside the originating vertex's direct connections, so that fewer steps are needed. 
                 
-**Memory Complexity:** Our flight search engine's BFS memory complexity is mostly determined by how the flight network graph and the queue used in the BFS algorithm are stored. This gives an O(V + E) complexity when accounting for the requirement to store each vertex and edge in the graph. Our implementation required careful attention to memory management, especially since we included return flights, which doubled the number of edges in the graph.


## Challenges and Solutions
- **Data Parsing:** The first challenge that we had was how to structure the data provided to us by the agency into a usable format for clojure, specifially when we considered how accurate it has to be for the engine to work. We solved this by seperating the string data into individual flight records (departure city, destination city, and price). We had to choose between using lists, vectors, or maps and even though lists and vectors offered ease in the iteration aspect, in a flight network representation, maps were more efficient because they provide faster access time which is more beneficial for BFS.
- **Managing return flights:** The list provided to us by the agency had 22 flights from departure to desintation city. When running the code without creating the return flights the options were very limited to clients. We had to come up with a way to create return flights so there were more flights options for clients by seperating data of the cities and prices into individual parts and by switching the places of (departure destination  cost) to (destination departure  cost) so the return flights were created.
- **User Input Validation and Handling:** Additionally, we came across another problem that was the fact tha the client had to input the name of the departure and destination. If they were to write "prague" instead of "Prague" the engine would not work. This was solved by adding the clojure function "clojure.string/capitalize" which capitalized each user input so the system can understand it based on the string data in it. 
- **BFS with condition:** We had to implement the engine with the condition of budget and connection limits of the clients. We first defined the Breadth-First search to find the routes and used this function in the prepare-travel-plan where we added the conditions for the budget and the connections of the flights , to ensure that the engine works in a efficiant way even with the added complexities.
-**Output:** Lastly, we noticed that when the user inputs their information and the search engine outputs the travel plan , there is no way for the user to re-start the engine. We fixed this issue by implementing lines of code for managing the application's control flow based on user input. This allow the user to either restart the engine or end it by exiting it. This is important for users who have not decided their destination city but are simply browsing for options for travelling.

## Result & Discussion

The flight search engine project showed how well different tools and methods work. We picked the BFS algorithm because it accurately finds the best routes by using user-defined parameters to find them. Using Clojure's advanced features, the system also showed strong data handling and processing, easily managing the large network of flight routes. The console-based interface was easy to use and gave users a good experience by checking their data carefully and fixing errors. The system was scalable and performed well, answering a wide range of user questions quickly and correctly. The project showed how important it is to choose the right algorithms when making software, especially for apps that need to process a lot of data, like flight search engines. 

In the future, there are improvements we can work on as the IT department. Some would be adding real-time flight information, making the system bigger so it has a graphics user interface, and adding advanced features like trips to more than one place, longer layovers, and ticket prices that change based on real-time demand. As shown by the project's successful execution and positive user feedback, functional programming can be used to solve real-world problems. The system could be further developed and improved, making it a more useful tool for planning trips.





