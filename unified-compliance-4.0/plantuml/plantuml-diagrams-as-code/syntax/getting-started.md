# Getting Started

## Basic Syntax

Every PlantUML file requires a start and end command. These will be the first and last lines of your code. X number of them use the same command a few of the supported non-UML diagrams have their own start and end commands. The table below shows the commands for each diagram.

|                          |                   |                 |
| ------------------------ | ----------------- | --------------- |
| **Diagram Type**         | **Start Command** | **End Command** |
| Sequence Diagram         | @startuml         | @enduml         |
| Use Case Diagram         | @startuml         | @enduml         |
| Class Diagram            | @startuml         | @enduml         |
| Object Diagram           | @startuml         | @enduml         |
| Activity Diagram         | @startuml         | @enduml         |
| Component Diagram        | @startuml         | @enduml         |
| Deployment Diagram       | @startuml         | @enduml         |
| State Diagram            | @startuml         | @enduml         |
| Network Diagram          | @startuml         | @enduml         |
| Salt or Wireframe        | @startsalt        | @endsalt        |
| Archimate Diagram        | @startuml         | @enduml         |
| Gantt Chart              | @startgantt       | @endgantt       |
| MindMap                  | @startmindmap     | @endmindmap     |
| Work Breakdown Structure | @startwbs         | @endwbs         |
| JSON                     | @startjson        | @endjson        |
| YAML                     | @startyaml        | @endyaml        |

#### Example: Basic PlantUML File

```
@startuml



@enduml
```

## Commenting Code

Comments in code are ignored by the program. Use them for planning or to explain to the next person (future you) what your code is doing. To comment in PlantUML put a single quote at the beginning of the line.

****

**Example: Commenting Code**

```
@startuml
'The above line is required for most PlantUML files.

'This line will be ignored by PlantUML.

'The below line is required for most PlantUML files.
@enduml
```

## Mixing Diagrams and Syntax Errors

PlantUML is used to make several types of diagrams. As shown above many of them are enclosed within the same @startuml and @enduml lines. Because of this PlantUML determines the type of diagram based on the body of your code. If you mix code from more than one type of diagram you may only receive a syntax error. If you continually get a syntax error and know there is nothing wrong with the particular line that is throwing the error, make sure you aren't accidentally using syntax from another type of diagram.

We will show this in the following three examples. The first two sets of code and images will make a proper diagram. The third set will combine the first two and throw a syntax error.

#### Example: Functional Sequence Diagram

```
@startuml

'The following code is used in a sequence diagram.

participant Sean
participant Maria

Sean  ->  Maria 
Sean  <-- Maria

@enduml
```

![Sequence Diagram](<../../../.gitbook/assets/GettingStarted03\_mixing\_syntax (1).png>)

#### Example: Functional Use Case Diagram

```
@startuml

'The following code is used in a use case diagram.

(Door)

:Sean:

Sean -> Door

@enduml
```

![Use Case Diagram](<../../../.gitbook/assets/GettingStarted03\_mixing\_syntax (2).png>)

#### Example: Broken Diagram

```
@startuml

'The following code is used in a sequence diagram.

participant Sean
participant Maria

Sean  ->  Maria 
Sean  <-- Maria

'The following code is used in a use case diagram.
'Because of the mixed code. PlantUML will throw an error on line 14.

(Door)

:Sean:

Sean -> Door

@enduml
```

![Broken Diagram](../../../.gitbook/assets/GettingStarted03\_mixing\_syntax.png)
