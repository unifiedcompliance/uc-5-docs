# Relations and Associations

## Declaring Relations

A basic relation contains two entities and a line showing the relation between them.

#### Example: Declaring Object Relations

```
@startuml
'Example: Declaring Object Relations

'Declare two objects.
object Object01
object Object02

'Create a relation between the two object.
Object01 - Object02

@enduml
```

![Declaring Object Relations](../../../../.gitbook/assets/Relations01\_declaration.png)

## Parts of Relations

Relations are comprised of three parts. Label is the only optional part.

* **entity** - the object for which a relation can be described in an object diagram, must have two
* **connection** - visual description of the relation between entities
* **label** - textual description of the relation between entities

## Entities

The connected entities can be objects, fields, map tables, cells, or packages. Objects, map tables, and packages are defined by their **name**. Fields and cells are defined by the parent object name followed by two colons (::) and the field or cell **text**.

* object
* field
* map table
* cell
* package

#### Example: Relation Entities

```
@startuml
'Example: Relation Entities

'Create two objects with fields.
object Object01 {
    Field01
}

object Object02 {
    Field02
}

'Create a map table with two cells.
map MyMapTable {
    Cell01 => Cell02
}

'Create a relation between the two objects.
Object01 - Object02

'Create a relation between the second object and a cell in the map table.
Object02 - MyMapTable::Cell01

@enduml
```

![Relation Entities](../../../../.gitbook/assets/Relations02\_entities.png)

## Labels

This text describes the relation between the connected **entities**.  You can format **labels** with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. **Labels** are not required.

#### Example: Relation Labels

```
@startuml
'Example: Relation Labels

'Create three objects.
object Object01 
object Object02
object Object03

'Create a relation between the first two objects.
'Use a label to explain that relation.
'Use creole to emphasize the text.
Object01 - Object02 : **Relation** //Text//

'Create a relation between the second two objects.
'Use a label to explain that relation.
'Use markup to add color and emphasis to the text.
Object02 - Object03 : <color #561D5E><b>Relation</b> <i>Text</i></color>

@enduml
```

![Relation Labels](../../../../.gitbook/assets/Relations03\_connections.png)

## Connections

The connection is the line between the entities. It can carry a lot of information. The only required portion of the connection is the dash (-) between the entities.

* **arrowhead** - determines the shape of the arrow head, one may be on each end of the connection
* **line\_type** - determines the type of line between the **entities**
* **line\_orientation** - determines the direction of the second entity in relation to the first entity
* **line\_color** - determines the color of the line making the connection
* **line\_thickness** - determines the thickness of the line between the entities

### Arrowheads

The connection can have an arrowhead on both ends. It must touch the dash that defines the connection.

Note: The following example will be shown with two dashes in the code to provide better aesthetics for the example image. See line orientation for further explanation.

#### Example: Arrowheads

```
@startuml
'Example: Relations Arrowheads

'Create connections with all arrowhead types.
Object01 --     Object02
Object03 <-->   Object04
Object05 <|--|> Object06
Object07 }--{   Object08
Object09 #--#   Object10
Object11 ^--^   Object12
Object13 *--*   Object14
Object15 +--+   Object16
Object17 o--o   Object18
Object19 x--x   Object20

@enduml
```

![Arrowheads](../../../../.gitbook/assets/Relations04\_1\_connections\_arrowhead.png)

![Arrowheads](../../../../.gitbook/assets/Relations04\_2\_connections\_arrowhead.png)

### Line Orientation

**Line\_orientation** determines the placement of an entity in relation to the connected entity. There are two options, default and relative directions.

#### Default

By default a single dash in the connection draws the relationship horizontally. Two dashes draws the relationship vertically. These are read left to right and then drawn from left to right and top to bottom.

#### Example: Line Orientation Default

```
@startuml
'Example: Line Orientation Default

'Create Five Objects
object Center
object Right
object Left
object Up
object Down

'Create relationships that point in all four directions.
'Use the default method.
Center - Right
Left - Center
Center -- Down
Up -- Center

@enduml
```

![Line Orientation Default](../../../../.gitbook/assets/Relations05\_line\_orientation.png)

#### Relative Directions

Relative directions are defined by always using two dashes for the connection and writing the relative direction between the dashes. These are read from left to write and then drawn in the relative direction.

#### Example: Line Orientation Relative Directions

```
@startuml
'Example: Line Orientation Relative Directions

'Create Five Objects
object Center
object Right
object Left
object Up
object Down

'Creat relationships that point in all four directions.
'Use relative directions.
Center -right- Right
Center -left- Left
Center -down- Down
Center -up- Up

@enduml
```

![Line Orientation Relative Direction](../../../../.gitbook/assets/Relations06\_line\_orientation\_relative.png)

### Line Types

The **line\_type** can change the connecting line to dashed or dotted. **Line\_type** is placed inside of square brackets inside of the connecting dashes. **Line\_type**, **line\_color** and **line\_thickness** can be placed in any order inside of the square brackets they are separated by commas.

#### Example: Line Types

```
@startuml
'Example: Relation Line Types

'Create three objects.
object Object01 
object Object02
object Object03

'Create a relation between the first two objects.
'Make the connection dashed.
Object01 -[dashed] Object02 

'Create a relation between the first two objects.
'Make the connection dotted.
Object02 -[dotted]- Object03 

@enduml
```

![Relation Line Types](../../../../.gitbook/assets/Relations07\_line\_type.png)

### Line Colors

The **line\_color** changes the connecting line's color. **Line\_color** is placed inside of square brackets inside of the connecting dashes with a hash symbol (#) before the color. You can define colors with a standard color name or hex code. **Line\_type**, **line\_color** and **line\_thickness** can be placed in any order inside of the square brackets they are separated by commas.

#### Example: Line Colors

```
@startuml
'Example: Relation Line Colors

'Create three objects.
object Object01 
object Object02
object Object03

'Create a relation between the first two objects.
'Make the connection dashed.
Object01 -[#009EA1] Object02 

'Create a relation between the first two objects.
'Make the connection dotted.
Object02 -[#darkcyan]- Object03 

@enduml
```

![Relation Line Colors](../../../../.gitbook/assets/Relations08\_line\_colors.png)

### Line Thickness

The **line\_thickness** changes the connecting line's width. **Line\_thickness** is placed inside of square brackets inside of the connecting dashes. **Line\_type**, **line\_color** and **line\_thickness** can be placed in any order inside of the square brackets they are separated by commas.

#### Example: Line Thickness

```
@startuml
'Example: Relation Line Thickness

'Create three objects.
object Object01 
object Object02
object Object03

'Create a relation between the first two objects.
'Make the connection dashed.
Object01 -[thickness=4] Object02 

'Create a relation between the first two objects.
'Make the connection dotted.
Object02 -[thickness=8]- Object03 

@enduml
```

![Relation Line Thickness](../../../../.gitbook/assets/Relations09\_line\_thickness.png)

### With All Properties

#### Example: Relations With All Properties

```
@startuml
'Example: Relations With All Properties

object Object01 
object Object02
object Object03

Object01 -[#darkcyan,dotted,thickness=4] Object02 : **Relation** //Text//
Object02 -[#009EA1,dashed,thickness=4]- Object03 : <color #561D5E><b>Relation</b> <i>Text</i></color>

@enduml
```

![Relations With All Properties](../../../../.gitbook/assets/Relations10\_all\_properties.png)

## Associations

Association objects can be used to show many to one relations. The association object is a diamond.

#### Example: Association Objects

```
@startuml
'Example: Association Objects

'Create three objects.
object Object01 
object Object02
object Object03

'Create an association object.
diamond Association01

'Create a relations between the first two objects and the association object.
Object01 --> Association01
Object02 --> Association01

'Create a relation between the association object and the third object.
Association01 --> Object03

@enduml
```

![Association Objects](../../../../.gitbook/assets/Relations11\_associations.png)
