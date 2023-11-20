---
description: >-
  Relationships show associations between different types of classes. For
  example a class named car has a relationship with a class named wheel.
---

# Relationships

## Declaration

A basic relationship contains two entities and a line showing the relationship between them.

#### Example: Declaring Relationships

```
@startuml
'Example: Declaring Relationships

'Create two classes.
class Car 
class Wheel

'Show a relationship between the two classes.
Car - Wheel

@enduml
```

![Declaring Relationships](../../../../.gitbook/assets/Relationships01\_Declaration.png)

## Parts of Relationships

Relationships are comprised of three parts. Label is the only optional part.

* **entity** - the object for which a relationship can be described in a class diagram, must have at least two
* **connection** - visual description of the relationship between entities
* **label** - textual description of the relationship between entities

## Entities

The connected entity can be a class, attribute, or method. Classes are defined by their **name**. Attributes and methods are defined by the class **name** that contains them followed by two colons (::) and the attribute or method **text**.

* class
* attribute
* method

#### Example: Relationship Entities

```
@startuml
'Example: Relationship Entities

'Create a class with a method and an attribute.
class Car {
    axle
    go()
}

'Create two more classes.
class Wheel
class Fuel

'Show a relationship between a class and a method.
Fuel - Car::go

'Show a relationship between an attribute and a class.
Car::axle - Wheel

@enduml
```

![Relationship Entities](../../../../.gitbook/assets/Relationships02\_entities.png)

## Labels

Though it comes last in syntax we will explain **label** before **connection**. This is a purely aesthetic issue. While **label** is not required much of the **connection** is drawn poorly if there is no **label**. It gets squished together.

* **label\_text** - the text describing the relationship between connected entities
* **read\_direction** - shows the direction a relationship is read

### Label Text

This text describes the relationship between the connected **entities**. **Label\_text** is not required even if **read\_direction** is used. You can format **label\_text** with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.

#### Example: Label Text

```
@startuml
'Example: Label Text

'Create a class with a method and an attribute.
class Car {
    axle
    go()
}

'Create two more classes.
class Wheel
class Fuel

'Show a relationship between a class and a method.
'Use a label to explain that relationship.
'Use creole to emphasize the text.
Fuel - Car::go : **requires** 

'Show a relationship between an attribute and a class.
'Use a label to explain that relationship.
'Use markup to add color and emphasis to the text.
Car::axle - Wheel : <color #561D5E><b>has</b></color>

@enduml
```

![Label Text](../../../../.gitbook/assets/Relationships03\_label\_text.png)

### Read Direction

A greater than or less than sign (><) used to show the direction a relationship is read. The sign may be placed before or after the label. **Read\_direction** is not required even if **label\_text** is used.

#### Example: Read Direction

```
@startuml
'Example: Read Direction

'Create a class with a method and an attribute.
class Car {
    axle
    go()
}

'Create two more classes.
class Wheel
class Fuel

'Show a relationship between a class and a method.
'Use a label to explain that relationship.
'Add a read direction.
Fuel - Car::go : requires <

'Show a relationship between an attribute and a class.
'Use a label to explain that relationship.
'Add a read direction.
Car::axle - Wheel : > has

@enduml
```

![Read Direction](../../../../.gitbook/assets/Relationships03\_label.png)

## Connections

The connection is the line between the entities. It can carry a lot of information. The only required portion of the connection is the dash (-) between the entities.

* **multiplicity** - defines number relationships between the entities, one may be on each end of the connection
* **arrowhead** - determines the shape of the arrow head, one may be on each end of the connection
* **line\_type** - determines the type of line between the **entities**
* **line\_orientation** - determines the direction of the second entity in relation to the first entity
* **line\_color** - determines the color of the line making the connection
* **line\_thickness** - determines the thickness of the line between the entities

### Multiplicity

Multiplicity defines number relationships between the connected entities. Multiplicity can exist on each end of the connection. It is written as a number or numbers between quotation marks. You can format **multiplicity** with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. In this example one car has between four and six wheels.&#x20;

#### Example: Multiplicity

```
@startuml
'Example: Multiplicity

'Create two classes.
Class Car
Class Wheel

'Show a relationship between the classes.
'Use a label with direction to explain that relationship.
'Add multiplicity with markup for emphasis and color.
Car "1" - "<color #561D5E><b>4..6</b></color>" Wheel : > has

@enduml
```

![Multiplicity](../../../../.gitbook/assets/Relationships05\_multiplicity.png)

### Arrowheads

The connection can have an arrowhead on both ends. It must touch the dash that defines the connection.

Note: The following example will be shown with two dashes in the code to provide better aesthetics for the example image. See [line orientation](relationships.md#line-orientation) for further explanation.

#### Example: Arrowheads

```
'Example: Arrowheads

'Create connections with all arrowhead types.
Class01 --     Class02
Class03 <-->   Class04
Class05 <|--|> Class06
Class07 }--{   Class08
Class09 #--#   Class10
Class11 ^--^   Class12
Class13 *--*   Class14
Class15 +--+   Class16
Class17 o--o   Class18
Class19 x--x   Class20

@enduml
```

![Arrowheads](<../../../../.gitbook/assets/Relationships06\_arrowhead (1).png>)

![Arrowheads](../../../../.gitbook/assets/Relationships06\_1\_arrowhead.png)

### Line Orientation

Line\_orientation determines the placement of a class in relation to the connected class. There are two options, default and relative directions.

#### Default

By default a single dash in the connection draws the relationship horizontally. Two dashes draws the relationship vertically. These are read left to right and then drawn from left to right and top to bottom.

#### Example: Line Orientation Default

```
@startuml
'Example: Line Orientation Default

'Create Five Classes
Class Center
Class Right
Class Left
Class Up
Class Down

'Create relationships that point in all four directions.
'Use the default method.
Center - Right
Left - Center
Center -- Down
Up -- Center

@enduml
```

![Line Orientation Default](<../../../../.gitbook/assets/Relationships07\_1\_line\_orientation (1).png>)

#### Relative Directions

Relative directions are defined by always using two dashes for the connection and writing the relative direction between the dashes. These are read from left to write and then drawn in the relative direction.

#### Example: Line Orientation Relative Directions

```
@startuml
'Example: Line Orientation Relative Directions

'Create Five Classes
Class Center
Class Right
Class Left
Class Up
Class Down

'Creat relationships that point in all four directions.
'Use relative directions.
Center -right- Right
Center -left- Left
Center -down- Down
Center -up- Up

@enduml
```

![Line Orientation Relative Directions](../../../../.gitbook/assets/Relationships07\_2\_line\_orientation.png)

### Line Type

The **line\_type** can change the connecting line to dashed or dotted. **Line\_type** is placed inside of square brackets inside of the connecting dashes. **Line\_type**, **line\_color** and **line\_thickness** can be placed in any order inside of the square brackets they are separated by commas.

#### Example: Line Types

```
@startuml
'Example: Line Types

'Create Four Classes
Class Car
Class Axle
Class Wheel
Class Driver

'Create a relationship with a standard line type.
Car - Axle

'Create a relationship with a dotted line type.
Axle -[dashed]- Wheel

'Create a relationship with a dashed line type.
Car -[dotted]- Driver

@enduml
```

![Line Types](../../../../.gitbook/assets/Relationships08\_line\_type.png)

### Line Colors

The **line\_color** changes the connecting line's color. **Line\_color** is placed inside of square brackets inside of the connecting dashes with a hash symbol (#) before the color. You can define colors with a standard color name or hex code. **Line\_type**, **line\_color** and **line\_thickness** can be placed in any order inside of the square brackets they are separated by commas.

#### Example: Line Colors

```
@startuml
'Example: Line Colors

'Create Four Classes
Class Car
Class Axle
Class Wheel
Class Driver

'Create a relationship with a standard line color.
Car - Axle

'Create a relationship with a hex code line color.
Axle -[#561D5E]- Wheel

'Create a relationship with a named color.
Car -[#cyan]- Driver

@enduml
```

![Line Colors](<../../../../.gitbook/assets/Relationships09\_line\_color (1).png>)

### Line Thickness

The **line\_thickness** changes the connecting line's width. **Line\_thickness** is placed inside of square brackets inside of the connecting dashes. **Line\_type**, **line\_color** and **line\_thickness** can be placed in any order inside of the square brackets they are separated by commas.

#### Example: Line Thickness

```
@startuml
'Example: Line Thickness

'Create Four Classes
Class Car
Class Axle
Class Wheel
Class Driver

'Create a relationship with a standard line color.
Car - Axle

'Create a relationship with a line thickness of 4.
Axle -[thickness=4]- Wheel

'Create a relationship with a line thickness of 8.
Car -[thickness=8]- Driver

@enduml
```

![Line Thickness](../../../../.gitbook/assets/Relationships10\_line\_thickness.png)

### With All Properties

#### Example: Relationships With All Properties

```
@startuml
'Example: Relationships With All Properties

class Car
class Wheel
class Fuel

Car "1" -[#blue,dashed,thickness=2]-> "4..8" Wheel : has >

Car -right[#561D5E,dashed,thickness=4]- "1..*" Fuel : needs >

@enduml
```

![Relationships With All Properties](../../../../.gitbook/assets/Relationships99\_everything.png)

## Written Relationships

Some relationships can be written as the class is declared. These written relationships are "extends" and "implements."

#### Example: Written Relationships

```
@startuml
'Example: Written Relationships

'Create one class and one interface.
class ClassA
interface Interface1

'Create a class that extends ClassA.
class ClassB extends ClassA

'Create a class that implements Class1.
class Class2 implements Interface1

@enduml
```

![Written Relationships](../../../../.gitbook/assets/WrittenRelationships99\_everything.png)



