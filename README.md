# Online Multiplayer Word Unscramble Game

## Project Overview

This project is an online multiplayer word unscramble game developed in Java, utilizing a client-server architecture. The game focuses on real-time, text-based communication, allowing multiple players to compete by unscrambling words provided by the server. The client-side features a user-friendly Graphical User Interface (GUI) built with Swing.

## Game Concept: Word Unscramble

The game features the "Second Game" concept as described in the project specifications[cite: 8].
* The server presents a series of **unordered words** to all connected players[cite: 8].
* Players must unscramble these words and send the **correctly ordered word** back to the server[cite: 8].
* The **winner is the fastest player** to correctly answer 5 questions (unscramble 5 words)[cite: 8].
* Once a player solves 5 questions, the game ends[cite: 8].

For example:
* Server presents: `Pplea` → Player answers: `apple` [cite: 8]
* Server presents: `Lmfi` → Player answers: `film` [cite: 8]
* Server presents: `Bleat` → Player answers: `table` [cite: 8]

## Key Features & Technologies

### Architecture & Communication
* **Client-Server Model:** The game operates on a robust client-server architecture, enabling remote players to connect and interact.
* **Sockets:** All network communication between the server and clients is handled using Java Sockets, providing an API for both UDP and TCP protocols. This facilitates real-time data transfer and action synchronization.
* **Real-time Communication:** Player actions (e.g., submitting an unscrambled word) are immediately transmitted to the server and broadcast to other players, ensuring synchronized game state and score updates.
* **Concurrency (Threads):** The server and clients utilize threads to manage multiple concurrent connections and game logic, allowing several players to participate simultaneously.
* **Text-Based Communication:** The primary mode of in-game communication (e.g., words, answers, messages) is text-based.

### Client-Side Features (GUI)
* **Graphical User Interface (GUI):** The client application boasts an intuitive GUI developed using Java Swing.
* **Event-Based Programming:** User interactions (button clicks, text input) trigger events that drive the game logic.
* **Model-View-Controller (MVC) Pattern:** The GUI design may incorporate the MVC pattern for better separation of concerns, improving maintainability and scalability.
* **View Hierarchy:** Components are structured within a clear view hierarchy for organized UI layout.

### Implemented Functions

The project was developed in two phases, covering the following functionalities:

**Phase 1 (Core Game Flow & Connectivity)**
* **Connect:**
    * Clients can connect to the server and register unique usernames[cite: 4, 6].
    * The server confirms successful connection to the client[cite: 6].
    * Displays the names of all currently connected players[cite: 6].
* **Pair Request:**
    * Clients can signal their desire to play a new game (e.g., via a "Play" button)[cite: 6].
    * The server manages available "rooms" and adds players to a waiting list, considering the maximum number of players per game[cite: 6].
* **Player Joined:**
    * Once a player is assigned to a waiting room, other players in that room are notified of the new member's arrival[cite: 6].
    * Lists all members currently in the same waiting room[cite: 6].
* **Game Started:**
    * The server initiates the game when either the maximum number of players for a game is reached or after a 30-second timeout (if more than one player is present)[cite: 6].
    * Players can view updated scores for all participants within their game[cite: 6].

**Phase 2 (Game Completion & Player Management)**
* **Player Leave Request / Disconnect:**
    * The server detects when a player leaves the network (e.g., application close) or explicitly quits the game[cite: 6].
    * An announcement is broadcast to all remaining players about the departure, and the player list is updated[cite: 6].
    * The game continues unless only one player remains[cite: 6].
* **Game Ended:**
    * This event is broadcast from the client (upon winning) to the server and then from the server to all other clients[cite: 6].
    * If the game timer ends and no winner is determined, a message clarifies this to all players[cite: 6, 12].
    * The winner list is displayed after the game[cite: 12].

## How to Run

To run the game, you will need a Java Development Kit (JDK) installed.

1.  **Compile:** Compile all Java source files for both the server and client components.
    ```bash
    javac SERVER.java GAME.java ...
    ```
2.  **Run Server:** Start the server application first.
    ```bash
    java SERVER
    ```
3.  **Run Clients:** Open separate terminals/command prompts for each client. You should run one client per player[cite: 8].
    ```bash
    java GAME
    ```


## Evaluation Notes

* Each group member has a thorough understanding of every detail in the project and can answer questions regarding the evaluation[cite: 8].
* Cheating or copying solutions is strictly prohibited and will result in zero grades for all involved teams[cite: 8].
