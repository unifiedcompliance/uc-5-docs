# Organization

## Group Inheritance

The majority of skin parameters will be covered in their own chapter. However, group inheritance has a very specific use for organizing class diagrams. If multiple classes point to the same class the relationship arrow can be merged with the skin parameter **groupInheritance** followed by a number. By changing the number we can determine the threshold for merging relationships. If the threshold is set to two any entity with two or more relationships with the same trajectory will have those relationships merged.

#### Example: No Group Inheritance&#x20;

```
@startuml
'Example: No Group Inheritance

'Create classes with multiple relationships ranging from one to four relationships.
A1 <|-- B1

A2 <|-- B2
A2 <|-- C2

A3 <|-- B3
A3 <|-- C3
A3 <|-- D3

A4 <|-- B4
A4 <|-- C4
A4 <|-- D4
A4 <|-- E4

@enduml
```

![No Group Inheritance](../../../../.gitbook/assets/Organization01\_1\_group\_inheritance.png)

#### Example: Group Inheritance Threshold 2

```
@startuml
'Example: Group Inheritance Threshold 2

'Set the class diagram to merge same trajectory relationships of two or more.
skinparam groupInheritance 2

'Create classes with multiple relationships ranging from one to four relationships.
A1 <|-- B1

A2 <|-- B2
A2 <|-- C2

A3 <|-- B3
A3 <|-- C3
A3 <|-- D3

A4 <|-- B4
A4 <|-- C4
A4 <|-- D4
A4 <|-- E4

@enduml
```

![Group Inheritance Threshold 2](../../../../.gitbook/assets/Organization01\_2\_group\_inheritance.png)

####

#### Example: Group Inheritance Threshold 4

```
@startuml
'Example: Group Inheritance Threshold 4

'Set the class diagram to merge same trajectory relationships of four or more.
skinparam groupInheritance 4

'Create classes with multiple relationships ranging from one to four relationships.
A1 <|-- B1

A2 <|-- B2
A2 <|-- C2

A3 <|-- B3
A3 <|-- C3
A3 <|-- D3

A4 <|-- B4
A4 <|-- C4
A4 <|-- D4
A4 <|-- E4

@enduml
```

![Group Inheritance Threshold 4](../../../../.gitbook/assets/Organization01\_3\_group\_inheritance.png)

## Packages

Packages are used for organizing classes in the class diagram. It is used for grouping classes together. The most basic package begins with the word "package" followed by the **name** of the package. Any classes belonging to the package are declared inside the body of the package. The body is defined by a set of curly braces.

#### Example: Package Declaration

```
@startuml
'Example: Organization Package Declaration

'Create a basic package with a name.
'Add one class to the package.
package Package1 {

  class Class1

}

@enduml
```

![Package Declaration](../../../../.gitbook/assets/Organization02\_package\_declaration.png)

### Name

The **name** is text that appears in the head of the package. The **name** can be a single word without quotation marks or it can be a string with quotation marks. Single word supports creole syntax for emphasis. The string method supports emphasis with creole and markup language. The string method also supports colors with markup language. You can define colors with a standard color name or hex code. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

#### Example: Package Name

```
@startuml
'Example: Package Name

'Create a basic package with a name.
'Add one class to the package.
'Use creole to emphasize the name.
package "__Package 1__" {

  class Class1

}

'Create a basic package with a name.
'Add one class to the package.
'Use markup to add color and emphasis to the name.
package "<color #561D5E><i>Package 2</i></color>" {

    class Class2

}

@enduml
```

![Package Name](../../../../.gitbook/assets/Organization03\_package\_name.png)

### Types

The **type** is set immediately after the **name,** wrapped in a double set of less than and greater than signs. There are six package **types**. The default package **type** is a folder.

#### Example: Package Types

```
'Example: Package Types

'Create a package with a name for all six package types.
'Add one class to each package.

package Node <<Node>> {
  class Class1
}

package Rectangle <<Rectangle>> {
  class Class2
}

package Folder <<Folder>> {
  class Class3
}

package Frame <<Frame>> {
  class Class4
}

package Cloud <<Cloud>> {
  class Class5
}

package Database <<Database>> {
  class Class6
}

@enduml
```

![Package Types](../../../../.gitbook/assets/Organization04\_package\_types.png)

### Body Color

The **body\_color** property determines the fill color of the drawn package entity. The **body\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

#### Example: Package Body Color

```
@startuml
'Example: Package Body Color

'Create a package with a name and a class.
'Assign a body_color.
package Package1 #009EA1 {
  class Class1
}

'Create a package with a name and a class.
'Assign a gradient to body_color.
package Package2 #009EA1/white {
  class Class2
}

@enduml
```

![Package Body Color](../../../../.gitbook/assets/Organization05\_package\_fill\_color.png)

### Line Color

The **line\_color** property determines the color of the line that draws the box of the package. The **line\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

Note: **Line\_color** gradients do not perform well on packages. They only affect the line under the package **name**.

#### Example: Package Line Color

```
@startuml
'Example: Package Line Color

'Create a package with a name and a class.
'Assign a line_color.
package Package1 #line:561D5E {
  class Class1
}

'Create a package with a name and a class.
'Assign a gradient to line_color.
package Package2 #line:561D5E/white {
  class Class2
}

@enduml
```

![Package Line Color](../../../../.gitbook/assets/Organization06\_package\_line\_color.png)

### Line Style

The **line\_style** property determines the type of line that draws the box of the class. The **line\_style** is defined by one of the three options below. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a semicolon (**;**) between them. No spaces are needed.

* line.dashed
* line.dotted
* line.bold

#### Example: Package Line Style

```
@startuml
'Example: Package Line Style

'Create a package with a name and a class.
'Make the line_style bold.
package Package1 #line.bold {
  class Class1
}

'Create a package with a name and a class.
'Make the line_style dashed.
package Package2 #line.dashed {
  class Class2
}

'Create a package with a name and a class.
'Make the line_style dotted.
package Package3 #line.dotted {
  class Class3
}

@enduml
```

![Package Line Style](../../../../.gitbook/assets/Organization07\_package\_line\_style.png)

### Body

The **body** of the package displays the classes that belong to the package. Classes that belong to the package should be written inside the **body** of the package. Relationships can be written inside or outside of the package body.&#x20;

#### Example: Package Body

```
@startuml
'Example: Package Body

'Create a package with a name and two classes.
'Create a relationship between the classes inside the package.
package PackageA {
  class ClassA1
  class ClassA2

  ClassA1 -- ClassA2
}

'Create a second package with a name and a class.
package PackageB {
  class ClassB1
}

'Create a relationship between a class from the first package and a class from the second class.
ClassA1 - ClassB1

@enduml
```

![Package Body](../../../../.gitbook/assets/Organization08\_package\_body.png)

### With All Properties

#### Example: Packages With All Properties

```
@startuml
'Example: Packages With All Properties

package __PackageA__ <<Database>> #E6E6E7;line:009EA1;line.dashed {
  class ClassA1
  class ClassA2

  ClassA1 -- ClassA2
}

package "<color #E6E6E7><i>Package B</i></color>" <<Cloud>> #561D5E|191C1F;line:E6E6E7;line.bold {
  class ClassB1
}

ClassA1 - ClassB1

@enduml
```

![Packages With All Properties](../../../../.gitbook/assets/Organization09\_package\_all\_properties.png)

## Namespaces

Namespaces are similar to packages. However, namespaces allow multiple packages to contain classes with the same name. This is not possible with packages. Relationships between classes inside of namespaces must use fully qualified names for the classes in the form of **namespace\_name**.**class\_name.**

Namespaces do not have as many properties as packages.

#### Example: Namespace Declaration

```
@startuml
'Example: Namespace Declaration

'Create a namespace with a name and a class.
namespace Home1 {
  class Resident
}

'Create a second namespace with a different name and an identically named class.
namespace Home2 {
  class Resident
}

'Create a relationship between the two identically named classes.
Home1.Resident - Home2.Resident

@enduml
```

![](../../../../.gitbook/assets/Organization09\_namespace.png)

### Name

The **name** is text that appears in the head of the package. The **name** must be a single word without spaces or special characters other than creole characters for underlining. Single word supports creole syntax for underlining however those creole characters are officially part of the **name**. See [Text Formatting](../text-formatting.md) for a list of creole.

#### Example: Namespace Name

```
@startuml
'Example: Namespace Names

'Create a namespace with a name and a class.
namespace Home1 {
  class Resident
}

'Create a second namespace with a different name and an identically named class.
'Use creole to underline the name.
namespace __Home2__ {
  class Resident
}

'Create a relationship between the two identically named classes.
Home1.Resident - __Home2__.Resident

@enduml
```

![Namespace Names](../../../../.gitbook/assets/Organization11\_namespace\_name.png)

### Body Color

The **body\_color** property determines the fill color of the drawn namespace entity. The **body\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. This property must come after a hash (**#**) sign and touch the hash sign.

#### Example: Namespace Body Color

```
@startuml
'Example: Namespace Body Color

'Create a namespace with a name and a class.
'Add a body_color.
namespace Home1 #E6E6E7{
  class Resident
}

'Create a second namespace with a different name and an identically named class.
'Use a gradient for the body color.
namespace Home2 #E6E6E7/561D5E {
  class Resident
}

'Create a relationship between the two identically named classes.
Home1.Resident - Home2.Resident

@enduml
```

![Namespace Body Color](../../../../.gitbook/assets/Organization12\_namespace\_bodycolor.png)

### Body

The **body** of the namespace displays the classes that belong to the namespace. Classes that belong to the namespace should be written inside the **body** of the namespace. Relationships can be written inside or outside of the namespace **body**.&#x20;

#### Example: Namespace Body

```
@startuml
'Example: Namespace Body

'Create a namespace with a name and two classes.
'Create a relationship between the classes inside the namespace.
namespace Home1 {
  class Resident
  class Owner

'Create a relationship between both classes in this namespace.
  Resident -- Owner
}

'Create a second namespace with a different name and one identically named class.
namespace Home2 {
  class Resident
}

'Create a relationship between the two identically named classes.
Home1.Resident - Home2.Resident

@enduml
```

![Name Space Body](../../../../.gitbook/assets/Organization13\_namespace\_body.png)

### With All Properties

#### Example: Namespace With All Properties

```
@startuml
'Example: Namespace With All Properties

namespace Home1 #E6E6E7{
  class Resident
  class Owner

  Resident -- Owner
}

namespace Home2 #E6E6E7/561D5E{
  class Resident
}

Home1.Resident - Home2.Resident

@enduml
```

![Namespace With All Properties](../../../../.gitbook/assets/Organization14\_namespace\_all\_properties.png)

### Automatic Namespace Creation

You can create namespaces automatically with the **namespaceSeparator** setting. When activating the setting pick two special characters and those will be your separator. The example below recreates the example from the namespace **body** property.

To turn off automatic namespace creation set the **namespaceSeparator** setting to "none".

Note: The namespaceSeparator must be used to identify specific classes now, instead of the default period between namespace and class.

#### Example: Automatic Namespace Creation

```
@startuml
'Example: Automatic Namespace Creation

'Designate a namespaceSeparator.
set namespaceSeparator ::

'Create a namespace with two classes.
class Home1::Resident
class Home1::Owner

'Create a relationship between both classes in this namespace.
Home1::Resident -- Home1::Owner

'Create a second namespace with one identically named class.
class Home2::Resident

'Create a relationship between the two identically named classes.
Home1::Resident - Home2::Resident

'Turn off automatic namespace creation.
set namespaceSeparator none

'Try to create another namespace and class similar to the previous namespaces and classes.
class Home3::Resident

@enduml
```

![Automatic Namespace Creation](../../../../.gitbook/assets/Organization15\_namespace\_automation.png)

## Visibility

There are three ways to affect the visibility of entities in a class diagram. PlantUML adjusts visibility from the top down. This allows you to hide a large unneeded portion of the diagram and just show what you need.

* hide - hides parts of the class diagram, the parts still take up space in the diagram
* show - shows a part of a class that might otherwise be hidden
* remove - removes parts from the class diagram, they no longer take up space

#### Example: Visibility Starting Point

Use the following code as the starting point for the rest of the visibility examples.

Note: We will be changing the background color to more easily track the size of the diagram. Skin parameters will be covered in their own section.

```
@startuml
'Example: Visibility Starting Point
skinparam BackgroundColor #E6E6E7

class Class1 <<Top>> {
  Method_1()
  Property_1
}

interface Interface2 <<Top>>

class Class3 {
  Method_3()
  Property_3
}

enum Enum4

Class1 -  Interface2
Class1 -- Class3

@enduml
```

![Visibility Starting Point](../../../../.gitbook/assets/Organization16\_1\_hide.png)

### Hiding Showing and Removing Classes

You can change the visibility of a class by following the key word with the class **name**. You can change the visibility of several classes at a time by replacing the class **name** with a **stereotype**.

#### Example: Hiding, Showing, and Removing Classes

Notice how the below code leaves space for Interface2 because it is only hidden. However the part of the diagram containing Class3 is completely removed because we removed Class3.

```
@startuml
'Example: Hiding Showing and Removing Classes
skinparam BackgroundColor #E6E6E7

class Class1 <<Top>> {
  Method_1()
  Property_1
}

interface Interface2 <<Top>>

class Class3 {
  Method_3()
  Property_3
}

enum Enum4

Class1 -  Interface2
Class1 -- Class3

'Hide all <<Top> stereotypes.
hide <<Top>>

'Unhide or show Class1.
show Class1

'Remove Class3.
remove Class3

@enduml
```

![Hiding Showing and Removing Classes](<../../../../.gitbook/assets/Organization16\_2\_hide (1).png>)

### Hiding and Showing Parts of Classes

You can adjust visibility on parts of classes by placing their property type after the visibility keyword. The following items are adjustable. You can be specify which class to adjust if you place the **name** or **stereotype** of the class before the property type.

* **members** - this will adjust visibility of all fields, attributes and methods
* **fields** or **attributes** - this will adjust visibility of all fields and attributes
* **methods** - this will adjust visibility of all methods
* **circle** - this will adjust the visibility of spots in the class heads
* **stereotype** - this will adjust the visibility of stereotypes in the class head

#### Example: Hiding and Showing Parts of Classes

```
@startuml
'Example: Hiding and Showing Parts of Classes
skinparam BackgroundColor #E6E6E7

class Class1 <<Top>> {
  Method_1()
  Property_1
}

interface Interface2 <<Top>>

class Class3 {
  Method_3()
  Property_3
}

enum Enum4

Class1 -  Interface2
Class1 -- Class3

'Hide all fields, attributes, and methods.
hide members

'Hide the spots in all "Top" stereotypes.
hide <<Top>> circle

'Show the methods for Class1.
show Class1 methods

@enduml
```

![Hiding and Showing Parts of Classes](../../../../.gitbook/assets/Organization16\_3\_hide.png)

### Hiding and Removing Empty and Unlinked Entities

By adding the keywords "empty" and "@unlinked" you can hide or remove unneeded entities from the class diagram.

#### Example: Empty and Unlinked Entities

```
@startuml
'Example: Empty and Unlinked Entities
skinparam BackgroundColor #E6E6E7

class Class1 <<Top>> {
  Method_1()
  Property_1
}

interface Interface2 <<Top>>

class Class3 {
  Method_3()
  Property_3
}

enum Enum4

Class1 -  Interface2
Class1 -- Class3

'Hide all empty fields, attributes, and methods.
hide empty members

'Remove all classes that do not have any relationships.
remove @unlinked

@enduml
```

![Empty and Unlinked Entities](../../../../.gitbook/assets/Organization16\_4\_hide.png)

### Positioning Classes With Hidden Relationships

You can hide relationships with the key word "hidden". In the example [Visibility Starting Point](organization.md#example-visibility-starting-point) Enum4 sticks out to the right. This makes the diagram wider than is needed. You can manually move it under Interface2 by creating a relationship between them and then hiding the relationship.

#### Example: Class Positioned With Hidden Relationship

```
@startuml
'Example: Class Positioned With Hidden Relationship
skinparam BackgroundColor #E6E6E7

class Class1 <<Top>> {
  Method_1()
  Property_1
}

interface Interface2 <<Top>>

class Class3 {
  Method_3()
  Property_3
}

enum Enum4

Class1 -  Interface2
Class1 -- Class3

'Use a hidden relationship to place Enum4 under Interface2.
Interface2 -[hidden]- Enum4

@enduml
```

![Class Positioned With Hidden Relationship](../../../../.gitbook/assets/Organization16\_5\_position\_with\_hidden.png)

## Page Breaks

If you need to split a diagram into multiple pages use the command "page" followed by the number of pages you want. The page number format is HxV where H is the number of pages horizontally and V is the number of pages vertically.&#x20;

When the images are generated they will be created from top to bottom and then left to right. A "page 3x2" named "Diagram" will produce six images with the below names that should be placed in the below order.

|            |            |            |
| ---------- | ---------- | ---------- |
| Diagram    | Diagram\_2 | Diagram\_4 |
| Diagram\_1 | Diagram\_3 | Diagram\_5 |

#### &#x20;Example: Page Breaks 3x2

```
@startuml
'Example: Page Breaks 3x2
skinparam BackgroundColor #E6E6E7

class Class1 <<Top>> {
  Method_1()
  Property_1
}

interface Interface2 <<Top>>

class Class3 {
  Method_3()
  Property_3
}

enum Enum4

Class1 -  Interface2
Class1 -- Class3

'Break the diagram into three columns and two rows.
page 3x2

@enduml
```

![](../../../../.gitbook/assets/Organization17\_page\_break.png) ![](../../../../.gitbook/assets/Organization17\_page\_break\_002.png) ![](../../../../.gitbook/assets/Organization17\_page\_break\_004.png)

![](../../../../.gitbook/assets/Organization17\_page\_break\_001.png) ![Page Breaks 3x2](../../../../.gitbook/assets/Organization17\_page\_break\_003.png) ![](../../../../.gitbook/assets/Organization17\_page\_break\_005.png)
