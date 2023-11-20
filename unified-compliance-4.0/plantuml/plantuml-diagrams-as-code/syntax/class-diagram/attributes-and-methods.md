# Attributes and Methods

The class **body** contains the  attributes and methods of the class. These are automatically placed in predetermined areas in the class **body**. **** Attributes **** appear in the upper portion of the body and methods appear in the lower portion.

## Declaration

Attributes and methods are declared with an **asset\_type** followed by **text**. Notice how the method text is placed in the lower portion of the class body even though it is above the attribute text in the code.

#### Example: Declaring Attributes and Methods

```
@startuml
'Example: Declaring Attributes and Methods

'Create a class.
class Class{

    'Add a method with asset_type and text.
    {method} Method_Text

    'Add an attribute with asset_type and text.
    {field} Attribute_Text
    
}

@enduml
```

![Declaring Attributes and Methods](../../../../.gitbook/assets/A\&M01\_declaration.png)

## Shorthand

Shorthand allows us to declare attributes and methods without the **asset\_type**. Shorthand attributes are just written as a string on one line. Shorthand methods are the same and end in a set of parentheses.&#x20;

Note: **asset\_type** will override shorthand. See line 15.

#### Example: Shorthand Attributes and Methods

```
@startuml
'Example: Shorthand Attributes and Methods

'Create a class.
class Class{

    'Add a method using shorthand.
    Method Text()

    'Add an attribute using shorthand.
    Attribute Text 1

    'Add an attribute with asset_type and text.
    'Put parentheses at the end of the text.
    {field} Attribute Text 2()
}

@enduml
```

![Shorthand Attributes and Methods](../../../../.gitbook/assets/A\&M02\_shorthand.png)

## Properties

Attributes and methods have four properties. When using the shorthand method the only required property is the **text**. If shorthand is not used **asset\_type** and text are both required.

* **asset\_state** - determines if the asset is abstract or static
* **asset\_type** - determines if the asset is an attribute or method, shown above in [Declaration](attributes-and-methods.md#declaration)
* **visibility** - determines the visibility of a method or attribute
* **text** - describes the attribute or method

### Asset State

The **asset\_state** property allows you to label attributes and methods as abstract or static. Abstract assets appear in italics. Static assets appear with an underline.

#### Example: Attributes and Methods Asset States

```
@startuml
'Example: Attributes and Methods Asset States

class Class{

    'Add an abstract attribute with an asset_type.
    {abstract} {field} attribute1

    'Add a static attribute using shorthand.
    {static} attribute2

    'Add a static method with an asset_type.
    {static} {method} method1

    'Add an abstract method using shorthand.
    {abstract} method2()

}

@enduml
```

![Attributes and Methods Asset States](../../../../.gitbook/assets/A\&M03\_5\_asset\_state.png)

### Visibility

When used, the **visibility** property is placed directly in front of the **text**.

* **-** - signifies a private attribute or method
* **#** - signifies a protected attribute or method
* **\~** - signifies a package private attribute or method
* **+** - signifies a public attribute or method

#### Example: Attribute and Method Visibility

```
@startuml
'Example: Attribute and Method Visibility

'Create a class.
class "Class Name"{

    'Add two attributes with all three properties.
    {field} -attribute1
    {field} #attribute2

    'Add two attributes with shorthand.
    'Add visibility properties.
    ~attribute3
    +attribute4

    'Add two methods with all three properties.
    {method} -method1
    {method} #method2

    'Add two attributes with shorthand.
    'Add visibility properties.
    ~method3()
    +method4()

}

@enduml
```

![Attribute and Method Visibility](../../../../.gitbook/assets/A\&M03\_visibility.png)

### Text

You can format **text** with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.

#### Example: Attribute and Method Text

```
@startuml
'Example: Attribute and Method Text

'Create a class.
class "Class Name"{

    'Add an attribute with an asset_type.
    'Use creole to emphasize the text.
    {field} **attribute1**

    'Add an attribute using shorthand.
    'Use markup to emphasize the text and add color.
    <color #561D5E><b>attribute2</b></color>

    'Add a method with an asset_type.
    'Use markup to emphasize the text and add color.
    {method} <color #561D5E><b>method1</b></color>

    'Add a method using shorthand.
    'Use creole to emphasize the text.  
    **method2()**

}

@enduml
```

![Attribute and Method Text](../../../../.gitbook/assets/A\&M04\_text.png)

### With All Properties

#### Example: Attributes and Methods With All Properties

```
@startuml
'Example: Attributes and Methods With All Properties

class Class{

    {abstract} {field} -**attribute1**

    {static} #<color #561D5E><b>attribute2</b></color>

    {static} {method} ~<color #561D5E><b>method1</b></color>

    {abstract} +**method2()**

}

@enduml
```

![Attributes and Methods With All Properties](<../../../../.gitbook/assets/A\&M99\_everything (1).png>)
