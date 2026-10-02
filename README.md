# CSI-2300-Project-Rubik-s-cube-timer
Project Name: Rubik's Cube Scrambler
Team Name: Solo Brew
Team members: Myles Collier

Build Desription: I will be building a Rubiks Scrambler for my CSI 2300 course project. This Scrambler will provide functionalities that will be useful to someone who solve Rubik's Cubes competitively so that they can practice. This project will mirror similar types of tools that are aids to speed cubers. 

The first function of this project will be a timer that acts as a stopwatch. Once this stopwatch has been used the time will be entered into a database and the stopwatch will be automatically reset for the next solve.

For the times that have been entered into the database certain information will be made such as best time, worst time, and mean solve time as well as the solve number being displayed.

There will also be a menu section for algorithms that are helpful to the solver so that they can can lookup whichever ones they mmay have forgotten or just want to refresh up on.


Why I want to build my project: I have been speed solving rubik's cubes and many other simlary twisty puzzles. I wanted to make something that I would like to use and that would be useful to me. In choosing this for my project I would also be able to take similar softwares that i have used and make the version that has all of the most helpful parts put together.

```mermaid
%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#ffffff', 'edgeLabelBackground':'#ffffff'}}}%%
graph TB

    subgraph userInterface["User Interface"]
        stats["Statistics Display"]
        menu["Algorithm Menu"]
        timer["Timer/Stopwatch"]
    end

    subgraph database["Data Layer"]
        solveDB[("Solve Times DB")]
    end

    subgraph calculations["Processing"]
        timerLogic["Timer Logic"]
        statsCalc["Statistics Calculator"]
        algorithmLookup["Algorithm Lookup"]
    end

    %% Edge definitions
    timer -->|start/stop/reset| timerLogic
    timerLogic -->|save time| solveDB
    solveDB -->|retrieve times| statsCalc
    statsCalc -->|calculate stats| stats
    stats -->|display best/worst/mean| userInterface

    menu -->|search/filter| algorithmLookup
    algorithmLookup -->|display algorithms| menu

    solveDB -->|query solve count| stats

    %% Styling definitions
    classDef interface fill:#f0f9ff,stroke:#3bb0e2,stroke-width:1px;
    classDef data fill:#f0fdf4,stroke:#4ade80,stroke-width:1px;
    classDef process fill:#f5f3ff,stroke:#a78bfa,stroke-width:1px;

    class userInterface,timer,menu,stats interface;
    class database,solveDB data;
    class calculations,timerLogic,statsCalc,algorithmLookup process;

    %% ARROW COLOR EDIT HERE:
    linkStyle default stroke:#3bb0e2,stroke-width:2px;
```
