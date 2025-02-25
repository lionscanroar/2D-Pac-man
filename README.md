# Pac-Man Game

### SOFT2201 2024 SID: (520268067)

## How to Run the Code

To run the Pac-Man game, follow these steps:

1. Run the following command in your terminal to compile, build, and run the game:

    ```bash
    gradle clean build run
    ```

2. Once the game window opens, the game will start after a few seconds. 


> Note: Make sure your laptop is computer larger than (448x576) to fully display the game window.

### Directory Structure
Ensure that the `config.json` and `new-map.txt` files are correctly located in the `src/main/resources` folder as follows:


## Design Patterns Implemented

This project uses multiple design patterns to organise and structure the code. Below are the patterns used and the classes involved:

### 1. **Adapter Pattern**
- **Target Interface**: `FrightenedGhostBehaviour`
- **Adapter**: `FrightenedGhostAdapter`
- **Adaptee**: `FrightenedGhostAdaptee`
- **Client**: `GhostImpl`

- The Adapter pattern allows `GhostImpl` to implement a frightened mode by adapting the behavior without directly modifying the class. The adapter encapsulates frightened behaviors, keeping `GhostImpl` independent of specific frightened mode implementations.

### 2. **Facade Pattern**
- **Facade**: `GameFacade`
- **Subsystem Classes**:
    - `GameEngine`
    - `GameWindow`
    - `Level` (Indirectly)

- The Facade pattern simplifies interaction with complex game subsystems by providing a unified interface through `GameFacade`, which controls core game operations. This centralisation reduces the dependencies needed to start and manage the game.

### 3. **Strategy Pattern**
- **Strategy Interface**: `ChaseStrategy`
- **Concrete Strategies**:
    - `BlinkyChaseStrategy`
    - `PinkyChaseStrategy`
    - `InkyChaseStrategy`
    - `ClydeChaseStrategy`
- **Context**: `GhostImpl`

- The Strategy pattern enables each ghost to adopt a unique chasing behavior by using separate strategy classes for each ghost type. This pattern enhances flexibility, as different chasing algorithms can be assigned to ghosts at runtime without altering `GhostImpl`.

## Important Considerations

- **JSON Configuration**: The game reads its configuration from the `config.json` file located in the `src/main/resources` folder. This file contains settings like the number of lives, ghost speeds, and mode durations.

- **Map Layout**: The map is defined in the `new-map.txt` file, located in the `src/main/resources` folder. This file controls the layout of the walls, pellets, and the initial positions of Pac-Man and the ghosts.

Make sure both the `config.json` and `new-map.txt` files are placed correctly in the resources folder, as the game relies on these for initialisation.


