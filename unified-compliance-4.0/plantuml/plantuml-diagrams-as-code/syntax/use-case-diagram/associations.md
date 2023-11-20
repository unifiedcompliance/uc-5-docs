# Associations

Associations define the link between two entities in the use case diagram. These links can be between an **actor** and a **use\_case,** two **actors**, or two **use\_cases**.&#x20;

## Declaration

To declare associations in use case diagrams use characters to draw the connection between the associated entities. The default association is defined by a double hyphen (**--**) between an **actor** and a **use\_case**.

#### Example: Association Declaration

```
@startuml
'Example: Association Declaration

'Create an association between Zarek and Stock.
:Zarek: -- (Stock)

@enduml
```

![Association Declaration](../../../../.gitbook/assets/Association01\_declaration.png)

## Properties

Associations have eight properties. **Entity\_1**, **entity\_2**, and **association\_type** are required.  The properties generally follow the below order. Direction is placed inside of the association type.

* **entity\_1** - an **actor** or **use\_case**
* **association\_type** - defined by a character drawing as a line or arrow
* **direction** - determines the direction that the association line or arrow is drawn
* **entity\_2** - an **actor** or **use\_case**
* **line\_color** - defines the color of the **association** line or arrow
* **line\_type** - defines the type of line drawn for the **association**
* **text\_color** - determines the color of the **text**
* **text** - can be used to explain the association

### Entity\_1 & Entity\_2

The entity fields contain either an **actor name** or **use\_case description**. If either has an **alias**, use the **alias**.

#### Example: Association Entities

```
@startuml
'Example: Association Entities

'Create an actor.
:Zarek:

'Create a use_case. 
(Stock)

'Create an association between the two entities.
Zarek -- Stock

@enduml
```

![Association Entities](<../../../../.gitbook/assets/Association02\_entities (1).png>)

### Association Type

Association\_type is determined by a character drawing of a line or arrow. The three association types are shown below.

* **--**    draws a line between the two entities
* **-- >** draws an arrow between the two entities
* **--|>** draws an open arrow between the two entities

#### Example: Association Type

```
@startuml
'Example: Association Type

'Create a single line association between two entities.
:Zarek: -- (Stock)

'Create an arrow association between two entities.
:Ivy: --> (Bag)

'Create an open arrow association between two entities.
(Cleaning) --|> (Mop)

@enduml
```

![Association Type](../../../../.gitbook/assets/Association03\_association\_type.png)

### Direction

There are three methods you can use to determine the direction of association lines.&#x20;

* **direction\_parameter** - a setting used to determine association direction
* **character\_drawing** - drawing the direction of the association with characters
* **directional\_word** - determines the direction of the arrow with words

Note: Mixing **direction\_parameter** with **character\_drawing** or **directional\_word** will result in the association line pointing the wrong direction.

#### Direction Parameter

The default direction for a use case diagram is top to bottom. The direction can be changed with the **direction\_parameter**.

#### Example: Direction Parameter

```
@startuml
'Example: Use Case Direction Parameter

'Change the default association direction  to left to right.
left to right direction

'Create a single line association between two entities.
:Zarek: -- (Stock)

'Create an arrow association between two entities.
:Ivy: --> (Bag)

'Create an open arrow association between two entities.
(Cleaning) --|> (Mop)

@enduml
```

![Direction Parameter](../../../../.gitbook/assets/Association05\_direction\_parameter.png)

#### Character Drawings

**Direction** can be determined by the number of dashes in the drawing as well as placement of the greater than or less than sign.

* &#x20; **-- >**  draws a downward arrow
* **- >**     draws an arrow to the right
* **< --**   draws an upward arrow
* &#x20; **< -**  draws an arrow to the left

#### Example: Direction Character Drawings

```
@startuml
'Example: Use Case Character Drawings

'Create an association with an arrow pointing right.
:Zarek: -> (Right)

'Create an association with an arrow pointing left.
(Left) <- :Ivy:

'Create an association with an arrow pointing down.
:Sean: --> (Down)

'Create an association with an arrow pointing up.
(Up) <-- :Maria:

@enduml
```

![Direction Character Drawings](<../../../../.gitbook/assets/Association04\_direction\_character\_drawings (1).png>)

#### Directional Words

**Direction** can be determined by adding directional words to the middle of the **association\_type** between the hyphens.

#### Example: Directional Words

```
@startuml
'Example: Use Case Directional Words

'Create an association with an arrow pointing right.
:Zarek: -Right-> (Right)

'Create an association with an arrow pointing left.
:Ivy:   -Left-> (Left)

'Create an association with an arrow pointing down.
:Sean:  -Down-> (Down)

'Create an association with an arrow pointing up.
:Maria: -Up-> (Up)

@enduml
```

![Directional Words](../../../../.gitbook/assets/Association06\_directional\_words.png)



### Line Color

The **line\_color** is defined by a standard color name or hex code. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

#### Example: Line Color

```
@startuml
'Example: Association Line Color

'Create an association with a colored line.
:Zarek: -- (Stock) #Blue

@enduml
```

![Line Color](../../../../.gitbook/assets/Association07\_line\_color.png)

### Line Type



The **line\_type** defines the texture of the exterior line of the actor. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

The **line\_types** are as follows.

* line.bold
* line.dashed
* line.dotted

#### Example: Line Type

```
@startuml
'Example: Association Line Type

'Create an association with a bold line.
:Zarek: -- (Bold) #line.bold

'Create an association with a dashed line.
:Zarek: -- (Dashed) #line.dashed

'Create an association with a dotted line.
:Zarek: -- (Dotted) #line.dotted

@enduml
```

![Line Type](../../../../.gitbook/assets/Association08\_line\_type.png)

### Text Color

The **text\_color** determines the color of the **text** and is defined by a standard color name or hex code. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

#### Example: Text Color

```
@startuml
'Example: Association Text Color

'Create an association with colored text.
:Zarek: -- (Stock) #text:blue : Text

@enduml
```

![Text Color](../../../../.gitbook/assets/Association09\_text\_color.png)

### Text

The **text** field can be used to describe the association between the two entities. **Text** supports creole for emphasis.

#### Example: Text

```
@startuml
'Example: Association Text

'Create an association with multiline text.
'Use creole for emphasis.
:Zarek: -- (Stock) : Text\n**Stuff**

@enduml
```

![Association Text](../../../../.gitbook/assets/Association10\_text.png)

### With All Properties

#### Example: Association With All Properties

```
@startuml
'Example: Association With All Properties

'Create an association with all properties.
:Zarek: -left- (Stock) #blue;line.dashed;text:green : Text\n**Stuff**

@enduml
```

![Association With All Properties](../../../../.gitbook/assets/Association11\_all\_properties.png)
