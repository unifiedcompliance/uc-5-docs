# Objects

Objects are the primary entity in an object diagram. Note these are not classes. Classes belong in [Class Diagrams](../class-diagram/).&#x20;

## Declaration

Objects are declared using the keyword "object" followed by the name of the object.

#### Example: Object Declaration

```
@startuml
'Example: Object Declaration

'Declare an object.
object MyObject

@enduml
```

![Object Declaration](../../../../.gitbook/assets/Objects01\_declaration.png)



## Properties

* **name** - the name in the header of the object
* **alias** - an alias for an object with a long name
* **stereotype** - a stereotype in the header of the object
* **fill\_color** - the color of the object
* **body** - the lower portion of the class, contains fields

### Name

The **name** is text that appears in the head of the object. The **name** can be a single word without quotation marks or it can be a string with quotation marks. The string method supports emphasis with creole and markup language. The string method also supports colors with markup language. You can define colors with a standard color name or hex code. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

Note: if you use the string method you _must_ assign an **alias** to the object.

### Alias

The **alias** is exactly that. It is a variable that represents an **object**. The variable for the alias follows the **as** keyword.

Note: if you use an alias the **name** _must_ be inside of quotation marks.

#### Example: Object Names and Aliases

```
@startuml
'Example: Object Names and Aliases

'Declare an object with a name.
object MyObject

'Declare an object with a name.
'Use creole for emphasis.
object "**MyOtherObject**" as MO

'Declare an object with a multiword name.
'Use markup for color and emphasis.
object "<color:#561D5E><i>Yet Another Object</i></color>" as PC

@enduml
```

![Object Names and Aliases](../../../../.gitbook/assets/Objects02\_name.png)

### Stereotype

The **stereotype** field is defined by text between a double set of greater than and less than signs. This adds a **stereotype** above the object **name**. This field can be a string without quotations. It supports creole for emphasis.

#### Example: Object Stereotype

```
@startuml
'Example: Object Stereotype

'Declare an object with a stereotype.
'Use creole for emphasis.
object MyObject <<A **Stereotype**>>

@enduml
```

![Object Stereotype](../../../../.gitbook/assets/Objects04\_stereotype.png)

### Fill Color

The **fill\_color** property determines the fill color of the drawn object. The **fill\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. This property must come after a hash (**#**) sign and touch the hash sign.

#### Example: Object Fill Color

```
@startuml
'Example: Object Fill Color

'Declare an object with a fill color.
object MyObject #009EA1
sa
@enduml
```

![Object Fill Color](../../../../.gitbook/assets/Objects05\_fill\_color.png)

### Body

The **body** of the object displays the fields that belong to the object. [Fields](objects.md#adding-fields) will be discussed later in this chapter.

#### Example: Object Body

```
@startuml
'Example: Object Body

'Declare an object with a body.
'Add a field to the body.
object MyObject{
  MyField
}

@enduml
```

![Object Body](../../../../.gitbook/assets/Objects06\_body.png)

### With All Properties

#### Example: Object With All Properties

```
@startuml
'Example: Object With All Properties

object "<color:#E6E6E7><i>My Object</i></color>" as MO <<A **Stereotype**>> #009EA1 {
  MyField
}

@enduml
```

![Object With All Properties](../../../../.gitbook/assets/Objects007\_all\_props.png)

### Fields

There are two ways to add fields to the **body** of an object. One is by listing the field inside the body of the object when the object is created. The other is by assigning the field to the object by using the object **name** or **alias**. Quotation marks are not required for multi-word fields.&#x20;

You can format fields with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.

#### Example: Adding Fields

```
@startuml
'Example: Adding Fields

'Declare an object with a body.
'Add a field to the body, use creole for emphasis.
object MyObject{
  **MyField**
  
}

'Declare an object with an alias and body.
'Add a field to the body, use markup for emphasis and color.
object "My Other Object" as MOO {
    <color:#009EA1><b>Another Field</b></color>

}

'Add a field to the first object, use markup for emphasis and color.
MyObject : <color:#561D5E><i>Yet Another Field</i></color>

'Add a field to the second object, use creole for emphasis.
MOO : The //Final// Field

@enduml
```

![Adding Fields](<../../../../.gitbook/assets/Objects08\_fields (1).png>)

## Map Table or Associative Array

The map table or associative array is a special type of object that holds a table or array in the body. It contains all of the same properties as a standard object. The only difference is the structure of the fields or cells.

#### Example: Map Table With All Properties

```
@startuml
'Example: Map Table With All Properties

map "<color:#E6E6E7><i>My Map Table</i></color>" as MT <<A **Stereotype**>> #009EA1 {
 cell_1 => cell_2 
}

@enduml
```

![Map Table With All Properties](../../../../.gitbook/assets/MapArray01declaration.png)

### Cells

Cells work similar to fields but they have an arrow in the middle of them. The arrow separates the line into two cells in the map table. Cells also support creole and markup like fields. When formatting cell text, treat each side of the arrow separately.

#### Example: Adding Cells

```
@startuml
'Example: Adding Cells

map MapTable {
    cell_1 => cell_2

}

map "My Map Table" as MT {
    <color:#561D5E><i>cell_1</i></color> => **cell_2**
}

MapTable : cell_3 => cell_4

MT : <color:#561D5E><b>cell_3</b></color> => <color:#009EA1><b>cell_5</b></color>

@enduml
```

![Adding Cells](../../../../.gitbook/assets/MapArray02\_cells.png)

