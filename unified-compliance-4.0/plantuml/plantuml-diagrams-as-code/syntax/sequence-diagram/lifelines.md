# Lifelines

Lifelines are the basic building block for sequence diagrams. They represent the participants that send and receive messages in sequence diagrams. The lifeline consists of a head with a name and a line drawn vertically down from the head. The default head is a rectangle with a name in it. PlantUML draws a foot as well. The foot is nice aesthetically but is not an official part of UML. We will leave it in our examples for aesthetic reasons.

## Declaration

Use the "participant" keyword followed by a **name** to declare a default lifeline. Lifelines automatically appear left to right in order of declaration.

#### Example: Declaring Lifelines

```
@startuml 
'Example: Declaring Lifelines

'Declare default lifelines and name them.
participant Sean
participant Maria
participant Zarek

@enduml
```

![Declaring Lifelines](../../../../.gitbook/assets/01\_Lifelines\_declaringLifelines.png)

## Properties

Properties following the **participant\_type** affect the format of the lifeline head. You are only required to use the **participant\_type** and **name** properties to declare a lifeline. There is some wiggle room with property order. For the sake of consistency and best practice we will keep them in the below order throughout this book. Below is a list of lifeline properties.&#x20;

* **participant\_type** - determines the head shape based on its classifier
* **name** - the text that appears in the head of the lifeline
* **display\_name** - a method for formatting **name**, comes after **name**
* **formatted\_name** - used in place of **name** and **display\_name**
* **variable\_name** - used as a variable for a lifeline with a long **name**&#x20;
* **back\_ground\_color** - sets the background color of the head
* **stereotype** - allows for the head to display a stereotype
* **order\_number** - adjusts the horizontal order of lifelines

### Participant Type

There are several options for **participant\_type**. Simply replace participant with any other **participant\_type**. The options are indicative of UML classifiers. PlantUML will change the header shape accordingly. Below is a list of participant types.

* participant
* actor
* boundary
* control
* entity
* database
* collections
* queue

#### Example: Participant Type

```
@startuml
'Example: Participant Type

'Declare lifelines with different head shapes.
participant participant
actor       actor
boundary    boundary
control     control
entity      entity
database    database
collections collections
queue       queue

@enduml
```

![Participant Type](../../../../.gitbook/assets/02\_Lifeline\_participant\_type.png)

### Name

The **name** is simply text that appears in the head of the lifeline. The **name** can be a single word without quotation marks or it can be a string with quotation marks. The string method supports line breaks.

#### Example: Name

```
@startuml
'Example: Name

'Declare a lifeline with a simple name
participant Sean

'Declare a lifeline with a name as a string
participant "Maria The Closer"

'Declare a lifleine with a multiline name
participant "Zarek \nThe Guy With \nCurly Hair"

@enduml
```

![Name](../../../../.gitbook/assets/03\_Lifelines\_name.png)

### Display Name

The **display\_name** property follows the "as" keyword. It can be used to display text in the head that is entirely different from the **name**. The **display\_name** property supports creole syntax for emphasis and markup language for color. You can define colors with a standard color name or hex code. Oddly PlantUML does not support emphasis with markup in the lifeline head. This lack of markup options is not in alignment with all PlantUML text fields. Luckily we can combine markup and creole. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

#### Example: Display Name

```
@startuml
'Example: Display Name

'Declare a lifeline with bold text using creole.
participant Sean as "**Juanito**"

'Declare a lifeline with purple text using markup.
participant Maria as "<color:#561D5E>Mija Mia</color>"

'Declare a lifeline with bold red text using markup and creole.
participant Zarek as "<color:#FF0000>**Zarek**</color>"

@enduml
```

![Display Name](../../../../.gitbook/assets/04\_Lifelines\_display\_name.png)

### Formatted Name

The **formatted\_name** property replaces **name** and **display\_name**. Similar to **display\_name** it supports creole syntax for emphasis and markup language for color. You can define colors with a standard color name or hex code. Once again PlantUML does not support emphasis with markup in the lifeline head. However we can still combine markup and creole. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

#### Example: Formatted Name

```
@startuml
'Example: Formatted Name

'Declare a lifeline with bold text using creole.
participant "**Juanito**"

'Declare a lifeline with purple text using markup.
participant "<color:#561D5E>Mija Mia</color>"

'Declare a lifeline with bold red text using markup and creole.
participant "<color:#FF0000>**Zarek**</color>"

@enduml
```

![Formatted Name](../../../../.gitbook/assets/05\_Lifelines\_formatted\_name.png)

### Variable Name

A **variable\_name** is just that, a variable. You can assign a lifeline to a variable using the "as" keyword. This practice eases utilization of a lifeline with a **formatted\_name**. Otherwise, you have to type the entire lifeline name, including formatting, every time you use that lifeline. To show this we will pass a few messages between our lifelines. Messages will not be explained here. See the [messages](messages.md) section for an in-depth explanation.

#### Example: Variable Name

```
@startuml
'Example: Variable Name

'Declare lifeline Sean with a formatted_name and a variable_name.
participant "**Juanito**" as Sean

'Declare lifeline Mija Mia with a formatted_name only.
participant "<color:#561D5E>Mija Mia</color>"

'Declare lifeline Zarek with a formatted_name and a variable_name.
participant "<color:#FF0000>**Zarek**</color>" as Zarek

'Send a message from Sean to Mia. It's fairly ugly and will quickly become cumbersome.
Sean -> "<color:#561D5E>Mija Mia</color>"

'Send a message from Juanito to Zarek. 
Sean -> Zarek

@enduml
```

![Variable Name](<../../../../.gitbook/assets/06\_Lifelines\_variable\_name copy.png>)

### Background Color

The **background\_color** property allows you to change the background color of the lifeline head. You can define colors with a standard color name or hex code. Create a gradient by using two colors. Notice that these colors can be used on any **participant\_type.**

**Example: Background Color**

```
@startuml
'Example: Background Color

'Declare lifeline Sean with a cyan background_color.
participant Sean #Cyan

'Declare lifeline Zarek with a red background_color.
actor Zarek #FF0000

'Declare lifeline Maria with a purple to black gradient background_color.
'Changes Maria's text color to white.
queue Maria as "<color:#White>Mia</color>" #561D5E/000000

@enduml
```

![Background Color](../../../../.gitbook/assets/07\_Lifelines\_background\_color.png)

### Stereotype

The **stereotype** property gives the ability to add a stereotype to the lifeline head. You can emphasize stereotype text with creole syntax and color it with markup. It is also possible to embed a colored circle with an internal character, or both. Define colors with a standard color name or hex code.

#### Example: Stereotype

```
@startuml
'Example: Stereotype

'Declare a participant with a cyan colored spot with a lower case Y in the spot.
participant Sean << (y,#00FFFF) >>

'Declare a participant with a stereotype that is bold and purple.
participant Maria << <color:#561D5E>**Middle Child**</color> >>

'Declare a participant with a red colored spot with a capital letter O in it
'Make it also have a stereotype
participant Zarek << (O,#FF0000) The Oldest >>

@enduml
```

![Stereotypes](../../../../.gitbook/assets/08\_Lifelines\_stereotype.png)

### Order Number

The **order\_number** property allows you to arrange lifelines regardless of their order in the code.

#### Example: Order Number

```
@startuml
'Example: Order Number

'Declare this lifeline first, but make it appear second.
participant "Maria the middle child" order 2

'Make this lifeline appear last.
participant "Sean the youngest" order 3

'Make this lifeline appear first.
participant "Zarek the oldest" order 1

@enduml
```

![Order Number](../../../../.gitbook/assets/09\_Lifelines\_order\_number.png)

## Undeclared Lifelines

You can create a sequence diagram without declaring lifelines. However, the lifelines will only have default properties. Lifelines are automatically generated as they appear in messages. This can be useful if you are putting together a quick sequence diagram without any bells or whistles.

#### Example: Undeclared Lifelines

```
@startuml
'Example: Undeclared Lifelines

'Send some messages without declaring any lifelines.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

Maria ->  Zarek : Text
Maria <-- Zarek : Text

Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Undeclared Lifelines](../../../../.gitbook/assets/Lifelines11\_undeclared\_lifelines.png)

## Participants Creating New Lifelines

A participant can create another participant, therefor starting a new lifeline. The creation commands are below.

* **create** - creates a lifeline on the following message line
* **\*\*** - shortcut for create that is used on the message line

Use the **create** command on the line before the creation message. Use the **\*\*** shortcut command immediately following the **name** of the created lifeline in the message line. To comply with UML standards, be sure to draw the creation message with a dashed line and an open arrow head. See lines 11 and 16 below. Messages are thoroughly covered in the [messages](messages.md) section.&#x20;

The new lifeline will not visually exist in the sequence diagram until _created_. However, if you want to adjust the new lifelines properties you will need to declare the lifeline ahead of time. Undeclared lifelines that are created with the **create** command have default properties just like the undeclared lifelines example above.

#### Example: Participants Creating New Lifelines

```
@startuml
'Example: Participants Creating New Lifelines

participant Sean

'Declare Maria as an actor with a purple background.
actor Maria #561D5E

'Make Sean create Maria.
create Maria
Sean -->> Maria: Creation Message
Sean -> Maria: Text

'Make Maria create Zarek.
'Use the shortcut method.
Maria -->> Zarek **: Creation Message
Maria -> Zarek: Text

Zarek --> Maria: Text
Maria --> Sean : Text

@enduml
```

![Participants Creating New Lifelines](../../../../.gitbook/assets/Lifelines10\_creation.png)

## Visibility

It is possible to hide the lifeline foot. It is also possible to hide lifelines that do not send or receive messages. You can do both the following **hide** commands.

* **hide footbox** - hides the lifeline foot from the sequence diagram drawing
* **hide unlinked** - hides all inactive lifelines

#### Example: Lifeline Visibility

```
@startuml
'Example: Lifeline Visibility

'Remove the lifeline feet.
hide footbox

'Hide inactive lifelines.
hide unlinked

'Declare three lifelines.
participant Maria
participant Sean
participant Zarek

'Send messages between only two lifelines.
Maria -> Sean : Text
Maria <- Sean : Text

@enduml
```

![Lifeline Visibility](../../../../.gitbook/assets/Lifelines12\_visibility.png)
