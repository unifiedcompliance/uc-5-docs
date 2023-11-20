# Arrows

## Declaration

Arrows do not require a declaration. They appear automatically in activity diagrams. Arrows generally appear between two actions that are vertically adjacent in the code.

#### Example: Arrow Declaration

## Properties

Arrows must be drawn in order to adjust their properties.

* **line\_color** - defines the color of line drawn for the **arrow**
* **line\_type** - defines the type of line drawn for the **arrow**
* **text** -can be used to explain the **arrow**

### Line Color

The **line\_color** is defined by a standard color name or hex code. If you use this property _alone_ it must come after a hash (**#**) sign and touch the hash sign. If any other properties follow this place a comma (**,**) between them. No spaces are needed.

#### Example: Arrow Line Color

```
@startuml
'Example: Arrow Line Color

'Declare an action.
:First Action;

'Give the arrow a color.
-[#0E7DC1]->

'Declare an action.
:Second Action;

@enduml
```

![Arrow Line Color](../../../../.gitbook/assets/Arrows02\_linecolor.png)

### Line Type

The **line\_type** defines the texture of the line drawing the arrow. If any other properties follow this place a comma (**,**) between them. No spaces are needed. The **hidden** line type completely removes the arrow.

The **line\_types** are as follows.

* line.bold
* line.dashed
* line.dotted
* line.hidden

#### Example: Arrow Line Type

```
@startuml
'Example: Arrow Line Type

'Declare an action.
:First Action;

'Give the arrow a bold line.
-[bold]->

'Declare an action.
:Second Action;

'Give the arrow a dashed line.
-[dashed]->

'Declare an action.
:Third Action;

'Give the arrow a dotted line.
-[dotted]->

'Declare an action.
:Fourth Action;

'Hide the arrow.
-[hidden]->

'Declare an action.
:Fifth Action;

@enduml
```

![Arrow Line Type](<../../../../.gitbook/assets/Arrows03\_linetype (2).png>)

### Text

The **text** property provides the text that is displayed near the arrow. Text immediately follows the coded arrow and ends with a semicolon (**;**).

This is also where the **text** is formatted. Arrow **text** supports creole for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with line breaks between the coded arrow and final semicolon (;). You can use as many lines as necessary. Empty lines will be displayed..

#### Example: Arrow Text

```
@startuml
'Example: Arrow Text

'Declare an action.
:First Action;

'Declare an arrow with multiline text.
->First

Arrow;

'Declare an action.
:Second Action;

'Declare an arrow.
'Use creole for text emphasis
-> **Second** //Arrow//;

'Declare an action.
:Third Action;

'Declare an arrow.
'Use markup for text color and emphasis.
-><color #009EA1>Third</color> <i>Arrow</i>;

'Declare an action.
:Fourth Action;

@enduml
```

![Arrow Text](../../../../.gitbook/assets/Arrows04\_text.png)

### With All Properties

#### Example: Arrows With All Properties

```
@startuml
'Example: Arrows With All Properties

:First Action;

-[dashed,#CD1E1E]->First

Arrow;

:Second Action;

-[#561D5E,bold]-> **Second** //Arrow//;

:Third Action;

-[dotted]-><color #009EA1>Third</color> <i>Arrow</i>;

:Fourth Action;

-[hidden]->You can place text
next to a hidden arrow;

:Fifth Action;

@enduml
```

![Arrows With All Properties](../../../../.gitbook/assets/Arrows05\_allprops.png)
