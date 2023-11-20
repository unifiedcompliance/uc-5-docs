# Actions and Other Objects

Actions are the primary item in an activity diagram.&#x20;

## Action Declaration

Basic actions are declared by placing text between a colon and semicolon. If more than one action is created. An arrow is automatically drawn between them working from the top down. However, you can manually draw the arrow between actions.

#### Example: Action Declaration

```
@startuml
'Example: Arrow Declaration

'Declare an action.
:First Action;

'Manually declare an arrow.
->

'Declare an action.
:Second Action;

@enduml
```

![Action Declaration](../../../../.gitbook/assets/Actions01\_declaration.png)

## Properties

* **fill\_color** - the fill color of the action
* **text** - the text inside of the action
* **specification** - the shape or specification of the action

### Fill Color

The **fill\_color** property determines the fill color of the action. The **fill\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. This property must come after a hash (**#**) sign and touch the hash sign.

#### Example: Action Fill Color

```
@startuml
'Example: Action Fill Color

'Declare an action.
:First Action;

'Declare an action and add a fill_color.
#009EA1:Second Action;

'Declare an action and add a gradient fill_color.
#CD1E1E-E6E6E7:Third Action;

@enduml
```

![Action Fill Color](../../../../.gitbook/assets/Actions02\_fillcolor.png)

### Text

The **text** property provides the text that is displayed in the action. This is also where the **text** is formatted. Action **text** supports creole for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with line breaks between the leading colon and final **shape** character. You can use as many lines as necessary. Empty lines will be displayed.

#### Example: Action Text

```
'Example: Action Text

'Declare an action with multiline text.
:First

Action;

'Declare an action.
'Use creole for text emphasis
:**Second** __Action__;

'Declare an action.
'Use markup for text color and emphasis.
:<color #009EA1>Third</color> <i>Action</i>;

@enduml
```

![Action Text](../../../../.gitbook/assets/Actions03\_text.png)

### Specification

The shape or specification of the action is determined by the final character of the action which is by default a semicolon. The following example shows the eight options. The fork command is only used here for aesthetics. It will be discussed in its own section later.&#x20;

#### Example: Action Specification

```
@startuml
'Example: Action Specification

:  ;  ;

fork
:  Less Than  <
:  Greater Than  >
:  Pipe |

fork again
:  Square Bracket  ]
:  Forward Slash  /
:  Back Slash  \\

endfork
: Curly Bracket }

@enduml
```

![Actions Shape](../../../../.gitbook/assets/Actions04\_shape.png)

### With All Properties

#### Example: Actions With All Properties

```
@startuml
'Example: Actions With All Properties

#009EA1:First

Action;

#CD1E1E:**Second** __Action__;

#561D5E/191C1F:<color #White>Third <i>Action</i></color>;

@enduml
```

![Actions With All Properties](../../../../.gitbook/assets/Actions05\_allprops.png)

## Connector Declaration

Connectors are declared by a single letter inside of a set of parentheses.

#### Example: Connector Declaration

```
@startuml
'Example: Connector Declaration

'Declare an action.
:First Action;

'Declare a connector.
(B)

'Declare an action.
:Second Action;

@enduml
```

![Connector Declaration](../../../../.gitbook/assets/Actions06\_connectors.png)

## Properties

* **fill\_color** - the fill color of the action
* **text** - the text inside of the action

### Fill Color

The **fill\_color** property determines the fill color of the connector. The **fill\_color** is defined by a standard color name or hex code. Create a gradient by using two colors. This property must come after a hash (**#**) sign and touch the hash sign. It is followed by a colon(**:**).

#### Example: Connector Fill Color

```
@startuml
'Example: Connector Fill Color

'Declare an action.
:First Action;

'Declare a connector.
'Add color.
#CD1E1E:(B)

'Declare a connector.
'Add a gradient.
#561D5E/White:(D)

'Declare an action.
:Second Action;

@enduml
```

![Connector Fill Color](../../../../.gitbook/assets/Actions07\_connectorfillcolor.png)

### Text

The **text** property provides the text that is displayed in the connector. The text must be a single character. Connector text does not support any formatting, neither creole nor markup, at the time of this writing.

#### Example: Connector Text

```
@startuml
'Example: Connector Text

'Declare an action.
:First Action;

'Declare a connector.
'Use a lower case letter.
(b)

'Declare a connector.
'Use a number.
(4)

'Declare a connector.
'Use a special character.
(:)

'Declare an action.
:Second Action;

@enduml
```

![Connector Text](../../../../.gitbook/assets/Actions08\_connectorText.png)

## Start, Stop, & End

The **start**, **stop**, and **end** objects are declared by the word itself. They have no other properties.

#### Example: Start, Stop

```
@startuml
'Example: Start, Stop

'Declare a start object.
start

'Declare an action.
:Action;

'Declare a stop object.
stop

@enduml
```

![Start, Stop](../../../../.gitbook/assets/Actions09\_startstop.png)

#### Example: End

```
@startuml
'Example: End

'Declare an action.
:Action;

'Declare an end object.
stop

@enduml
```

![End](../../../../.gitbook/assets/Actions10\_end.png)
