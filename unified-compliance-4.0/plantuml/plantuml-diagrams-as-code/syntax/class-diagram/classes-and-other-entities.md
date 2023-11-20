# Classes and Other Entities

Classes are the basic component of class diagrams. They describe the structure and features of the related objects on a class diagram.

## Declaration

Classes are declared with a class **type** followed by a **name**. The simplest class **type** is "class." A class name is typically capitalized in UML.

#### Example: Declaring Classes

```
@startuml
'Example: Declaring Classes

'Create a basic class with a name.
class Name

@enduml
```

![Declaring Classes](../../../../.gitbook/assets/Classes01\_declaration.png)

## Shorthand



## Properties

Classes have 11 properties. The only mandatory properties are **type** and **name**.

* **type** - determines the type of class
* **name** - name of the class
* **alias** - gives the ability to use a variable to identify the class
* **generic** - gives the class an optional descriptor
* **stereotype** -applies a stereotype text to the class
  * **spot\_letter** - defines the letter in the spot in the head of the class
  * **spot\_color** - determines the fill color of the spot in the head
* **body\_color** - determines the fill color of the class body
* **header\_color** - determines the fill color of the class head
* **line\_color** - determines the color of the line that draws the class&#x20;
* **line\_style** - determines the style of the line that draws the class
* **text\_color** - determines the color of the text in the class
* **body** - the portion of the class that holds its attributes and methods

### Type

There are several options for class **type**. Simply replace class with any other class **type**. PlantUML will change the Spot letter and emphasis of the **name** based on the class type. Below is a list of class **types**. Annotation displays an @ sign in the spot while the others display the first letter of their **type**. The last three will appear with an italicized name.&#x20;

* **annotation**
* **class**
* **entity**
* **enum**
* **interface**
* **abstract**&#x20;
* **abstract** **class**&#x20;

Note: abstract and abstract class perform identically.

#### Example: Class Types

```
@startuml
'Example: Class Types

'Display all 7 basic class types with names.
annotation      annotation
class           class
entity          entity
enum            enum
interface       interface
abstract        abstract
abstract class  abstract_class

@enduml
```

![Class Types](../../../../.gitbook/assets/Classes02\_type.png)

### Name

The **name** is text that appears in the head of the class. The **name** can be a single word without quotation marks or it can be a string with quotation marks. Single word supports creole syntax for emphasis. The string method supports emphasis with creole and markup language. The string method also supports colors with markup language. You can define colors with a standard color name or hex code. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

#### Example: Class Name

```
@startuml
'Example: Class Name

'Create a class with a single word name.
'Use creole for emphasis
class ~~Store~~

'Create a class with a name using the string method.
'Use markup for emphasis and color.
class "<color:#561D5E><b>Personal Care</b></color>"

@enduml
```

![Class Names](../../../../.gitbook/assets/Classes03\_name.png)

### Alias

The **alias** is exactly that. It is a variable that represents a **class**. It is especially useful if the **class** has a long **name**. The variable for the alias follows the **as** keyword.

There will be a **relationship** in the following example. This is needed to show the importance of the **alias**. Relationships will not be explained here. See the [relationships](relationships.md) section of this chapter for proper explanations.

Notice how much easier it is to use the PersCare **alias** on line 14. Otherwise you must write the entire **name** as shown for Department Store.

#### Example: Class Alias

```
@startuml
'Example: Class Alias

'Create a multiword class with a name using the string method.
'Use markup for emphasis and color.
class "<color:#Purple><b>Department Store</b></color>"

'Create a class with a name using the string method.
'Use markup for emphasis and color.
'Give it an alias.
class "<color:#561D5E><b>Personal Care</b></color>" as PersCare

'Show a relationship between the two classes.
"<color:#Purple><b>Department Store</b></color>" <- PersCare

@enduml
```

![Class Alias](../../../../.gitbook/assets/Classes04\_alias.png)

### Generic

The **generic** is an extra text field that attaches to the class head for further description. It is defined between a single set of greater than and less than signs. This field can be a string without quotations. It supports creole for emphasis. This is not the UML **stereotype** field.

#### Example: Class Generics

```
@startuml
'Example: Class Generic

'Create a class.
'Add a generic.
class Store <generic descriptor>

'Create a class.
'Add a generic.
'Use creole for emphasis.
class "Personal Care" <**generic descriptor**>

@enduml
```

![Class Generics](../../../../.gitbook/assets/Classes05\_generic.png)

### Stereotype

The **stereotype** field is defined by text between a double set of greater than and less than signs. This adds a **stereotype** above the class **name**. The **stereotype** text will be displayed in the color of the **text\_color** property. This field can be a string without quotations. It supports creole for emphasis.

#### Example: Class Stereotypes

```
@startuml
'Example: Class Generic

'Create a class.
'Add a stereotype.
class Store <<Focus>>

'Create a class.
'Add a stereotype.
'Add emphasis with creole.
class "Personal Care" <<**Auxiliary**>>

@enduml
```

![Class Stereotypes](../../../../.gitbook/assets/Classes06\_stereotype.png)

#### Spot Letter

The **stereotype** property contains three sub-properties. The first is the **spot\_letter**. This allows you to chose the letter that appears inside the circle on the left side of the class head. The **spot\_letter** is defined by placing a letter and its color inside a set of parentheses inside of the stereotype field. This letter will be the color defined by **text\_color**. If you use **spot\_letter** you must also define a **spot\_color**.

#### Spot Color

The second stereotype sub-property is **spot\_color**.  This allows you to chose the color that appears inside the circle on the left side of the class head. The **spot\_color** is defined by placing a standard color name or hex code inside a set of parentheses inside of the stereotype field. If you use **spot\_color** you must also define a **spot\_letter**.

#### Example: Class Spot Letter and Spot Color

```
@startuml
'Example: Class Generic

'Create a class.
'Change the spot_letter and spot_color.
class Store << (S,darkgrey) >>

'Create a second class.
'Add a stereotype.
'Change the spot_letter and spot_color.
class "Personal Care" << (P,#FF7700) >>

@enduml
```

![Class Spot Letter](<../../../../.gitbook/assets/Classes07\_spot\_letter (1).png>)

### Body Color

The **body\_color** property determines the fill color of the drawn class entity. The **body\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

Note: If used with the **header\_color** property, **header\_color** will determine the color of the header. If used alone **body\_color** will determine the color of the entire class.

#### Example: Class Body Color

```
@startuml
'Example: Class Body Color

'Create a class.
'Add body_color.
class Store #back:purple;

'Create a class.
'Add a body_color with a gradient.
class "Personal Care" #back:561D5E/FFFFFF;

@enduml
```

![Class Body Color](../../../../.gitbook/assets/Classes08\_body\_color.png)

### Header Color



The **header\_color** property determines the fill color of the drawn class header. The **header\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

Note: If used with **body\_color**, the color of the header will be different than the body of the class. If used alone the body of the class will be the default color.

#### Example: Class Body Color

```
@startuml
'Example: Class Header Color

'Create a class.
'Add header_color.
class Store #header:purple

'Create a class.
'Add a body_color with a gradient.
'Add a header color.
class "Personal Care" #back:561D5E/FFFFFF;header:purple

@enduml
```

![Class Header Color](../../../../.gitbook/assets/Classes09\_header\_color.png)

### Line Color

The **line\_color** property determines the color of the line that draws the box of the class. The **line\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

#### Example: Class Line Color

```
@startuml
'Example: Class Line Color

'Create a class.
'Add line_color.
class Store #line:purple

'Create a class.
'Add line_color with a gradient.
class "Personal Care" #line:561D5E/FFFFFF

@enduml
```

![Class Line Color](../../../../.gitbook/assets/Classes10\_line\_color.png)

### Line Style

The **line\_style** property determines the type of line that draws the box of the class. The **line\_style** is defined by one of the three options below. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

* line.dashed
* line.dotted
* line.bold

#### Example: Class Line Style

```
@startuml
'Example: Class Line Style

'Create a class.
'Leave a default line_style.
class Business 

'Create a class.
'Use a dashed line_style.
class Store #line.dashed

'Create a class.
'Use a dotted line_style.
class "Personal Care" #line.dotted

'Create a class.
'Use a bold line_style.
class Cooking #line.bold

@enduml
```

![Class Line Style](../../../../.gitbook/assets/Classes11\_line\_style.png)

### Text Color

The **text\_color** property determines the color of the text in the class. The **text\_color** is defined by a standard color name or hex code. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

#### Example:  Class Text Color

```
@startuml
'Example: Class Text Color

'Create a class.
'Add text_color.
class Store #text:purple

'Create a class.
'Add text_color.
class "Personal Care" #text:561D5E

@enduml
```

![Class Text Color](<../../../../.gitbook/assets/Classes12\_text\_color (1).png>)

### Body

The body of the class displays the attributes and methods that belong to the class. The body automatically sorts attributes and methods into their predefined areas. Attributes and methods will be discussed in their own chapter.

#### Example: Class Body

```
@startuml
'Example: Class Text Color

'Create a class with a body.
'Add one attribute and one method.
class Store {
    attribute
    method()
}

@enduml
```

![Class Body](<../../../../.gitbook/assets/Classes13\_body (1).png>)

### With All Properties

#### Example: Class With All Properties

```
@startuml
'Example: Class With All Properties

class "class_name" as alias <generic> << (N,orchid) stereotype>> #back:blue/red;header:purple;line:white;line.dotted;text:white {
    attribute
    method()
}

@enduml
```

![Class With All Properties](../../../../.gitbook/assets/Classes99\_everything.png)

## Other Entities

There are two other entities that are declared similar to classes. Both have a shorthand version for declaration. The diamond does not display the class **name**.

* **diamond** - class type command for creating a diamond entity
* **<>** - shorthand for creating a diamond
* **circle** - class type command for creating a circle entity
* **()** - shorthand for creating a circle

## Properties

Circle entities support the below list of class properties as seen in the above classes description. Diamond entities only support **type** and **name**.

* **type** - determines the type of class, circle or diamond
* **name** - name of the class, will not display for diamonds
* **body\_color** - determines the fill color of the class body
* **line\_color** - determines the color of the line that draws the class&#x20;
* **line\_style** - determines the style of the line that draws the class
* **text\_color** - determines the color of the text in the class

#### Example: Circle and Diamond Entities

```
@startuml
'Example: Circle and Diamond Entities

'Create a circle.
circle circle_name_1

'Create a circle with shorthand.
'Change all available properties.
() circle_name_2 #back:blue/red;line:white;line.dotted;text:blue

'Create a diamond.
diamond diamond_name_1 

'Create a diamond with shorthand.
<> diamond_name_2

@enduml
```

![Circle and Diamond Entities](../../../../.gitbook/assets/Classes14\_circle.png)
