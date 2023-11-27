# Flight-search engine
Welcome to the airline Search Engine, a reliable platform that assists in locating optimal airline itineraries between different cities. This efficient search engine, built on the Clojure programming language, facilitates the exploration of optimal travel choices according to individual preferences.

## Getting Started

You have two options for build tools to set up and execute this project: Clojure CLI tools (deps.edn) or Leiningen (Lein).

### Using Leiningen (Recommended)

1. Install Leiningen if you haven't already. Follow the instructions at [Leiningen's official website](https://leiningen.org/#install) for installation.
2. Clone this repository: git clone
3. Change into the project directory: cd flight-search
4. To build and run the project, use Leiningen's commands. For example, to start the application: lein-run

### Using Clojure CLI Tools

1. Install Clojure CLI tools if you haven't already. Follow the instructions at [Clojure's official website](https://clojure.org/guides/getting_started) for installation
2. Clone this repository: git clone
3. Change into the project directory: cd flight-search
4. To build and run the project, use Clojure CLI tools. For example, to start the application: clj -m flight-search.core

For your project, select the build tool that you feel most at ease with or that you prefer.


## Usage

### Input
1. Enter the city of departure.
2. Enter the city of destination.
3. Specify if you are on an organized trip (type 'g') or as part of a family (insert 'f').

### Passanger types

* Families with three members: Resort towns are where they are going. They are only able to afford two flights and three connections.
* Planned trips for five people: The cities they are going to are iconic cities. They are only able to afford four flights and three connections.

### Search result
* A number of route possibilities that fit your parameters will be shown by the search engine.
* The route inform ation, total cost per passenger, and the number of flights will all be included in each option.
* You can select the one that most closely matches your personal preferences.

## Contributing

This respitory is not dedicated for exteral use. No pull requests are available.
