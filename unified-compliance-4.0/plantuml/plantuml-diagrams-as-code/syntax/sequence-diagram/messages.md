# Messages

Messages are the basic action of sequence diagrams. They are portrayed by arrows going from a sender to a receiver.&#x20;

Lifelines will not be declared in this section unless required for an explanation. This will keep our code blocks smaller and easier to read.

## Declaration

In PlantUML, you declare messages by drawing an arrow with the characters on your keyboard. Place the arrow between the **sender** and the **receiver** with the arrow pointing at the **receiver**.&#x20;

#### Example: Message Declaration

```
@startuml
'Example:Message Declaration

'Send a few basic messages.
Sean  ->  Maria
Maria ->  Zarek

@enduml
```

![Message Declaration](../../../../.gitbook/assets/Messages01\_declaration.png)

## Direction

Arrows can be drawn right to left or left to right. This is nice as it allows you to customize how you want to format your messages. You can always keep senders on one side of your messages like the top of our example. You can also let your arrows go back and forth while your senders stay in the same place on consecutive lines like the bottom of our example. There is also the unadvised option of not picking a method. Do what makes sense for you and your team.

#### Example: Message Direction

```
@startuml
'Example: Message Direction

'Send a few messages back and forth between Sean and Maria.
'Keep Sean on the left of the code.
Sean  ->  Maria
Sean  <-  Maria
Sean  ->  Maria

'Send a few messages back and forth between Maria and Zarek.
'Keep the arrow pointing to the right in the code.
Maria -> Zarek
Zarek -> Maria
Maria -> Zarek

@enduml
```

![Message Direction](../../../../.gitbook/assets/Messages02\_direction.png)



## Properties

The minimum requirements for a message are **sender**, **line\_type**, **head\_type**, and **receiver**. As we did with lifelines we will keep all message properties except **message\_text** in the below order throughout this book. Keep in mind the order is sender to receiver as shown above, not necessarily left to right. The **message\_text** property is always furthest to the right.

* **sender** - the entity sending the message, usually a participant's lifeline
* **line\_type** - determines if the message arrow has a solid or dashed line
* **arrow\_color** - sets the color of the message arrow
* **arrow\_head** - determines the shape of the arrow head
* **receiver** - the entity receiving the message at the pointy end of the arrow, usually a participants lifeline
* **message\_text** - the text that appears with the message arrow

### Senders & Receivers

Senders and receivers are usually the participants with lifelines discussed in the previous section. There are a few exceptions. Messages that come from or go to places outside the scope of the current diagram have gates as their sender or receiver at the edge of the diagram. Other messages may get lost or we may not know where they come from. Per UML standards these lost and found messages are sent or received from a circle. PlantUML doesn't have a standalone command for this, so we have to combine gates with our circle. UML calls for a solid circle but PlantUML only supports an open circle. At the time of this writing PlantUML does not properly display found messages originating from the right side gate.

**Senders** and **receivers** that are not lifelines with **names** must touch the **arrow\_head**. See the list of **senders** and **receivers** below.&#x20;

A message can have the same **sender** and **receiver**.

* **name** - the name of a lifeline
* **\[** - signifies a gate touching the left side of the sequence diagram can be a sender or receiver
* **]** - signifies a gate touching the right side of the diagram can be a sender or receiver
* **o**- used as the **sender** of a found message or the **receiver** of a lost message, this is a lower-case letter o
* **?** - a special character used to shorten the length of a message arrow

#### Example: Sender & Receiver

```
@startuml
'Example: Messages Sender & Receiver

'Make Sean receive a message from a left gate
[-> Sean : Text

'Send a message from Sean to Maria.
Sean -> Maria : Text

'Send a message from Maria to herself.
Maria -> Maria: Text

'Send a message from Sean to a left gate.
Sean ->[ :Text

'Send a found message to Maria from the left.
[o-> Maria : Text

'Send a lost message from Maria to the right.
Maria ->o] : Text

'Send a message with a shortened arrow from Sean to the right.
Sean ->? : Text

'Send a message with a shortened arrow to Maria from the left.
?-> Maria : Text

@enduml
```

![Sender and Receiver](<../../../../.gitbook/assets/Messages03\_sender\_receiver (1).png>)

### Line Type

There are two basic **line\_types**, solid and dashed. Solid lines are for basic messages. Dashed lines are for replies and lifeline creation messages. Creation messages are covered in the [Participants Creating New Lifelines](lifelines.md#participants-creating-new-lifelines) section of [Lifelines](lifelines.md).

* "**-**" - creates a solid line
* "**--**" - creates a dashed line

#### Example: Line Type

```
@startuml
'Example: Messages Line Type

'Send a message from Sean to Maria.
Sean  ->  Maria : Text

'Sendd a reply from Maria to Sean.
Sean  <-- Maria : Text

@enduml
```

![Line Type](../../../../.gitbook/assets/Messages04\_line\_type.png)

### Arrow Colors

You can define **arrow\_color** with a standard color name or hex code placed between the **line\_type** and **arrow\_head**. Enclose the **color** with square brackets. Note that the circle for lost and found messages will be the same color as the arrow.

#### Example: Arrow Color

```
@startuml
'Example: Messages Arrow Color

'Send a message with a cyan colored arrow from Sean to Maria.
Sean -[#cyan]>  Maria : Text

'Send a reply message with a purple arrow from Maria to Sean.
Sean <[#561D5E]-- Maria : Text

'Send a lost message with a red arrow from Zarek to the right
Zarek -[#FF0000]>o] : Text

@enduml
```

![Arrow Color](../../../../.gitbook/assets/Messages05\_arrow\_color.png)

### Arrow Heads

UML standards for sequence diagrams describe three options for **arrow\_heads**. A filled **arrow\_head** represents a synchronous message. An open **arrow\_head** represents an asynchronous message. An X or cross represents an object deletion message. For more on object deletion messages see [ExecutionSpecification](executionspecification.md). PlantUML provides us with several more options for increased personalization. These will be attached to a reply **line\_type** in the following list for easier visualization. Be mindful the backslashes in the example as they are still escape characters in the **message\_text**.

* \-- > filled **arrow\_head** right
* \-- >> open **arrow\_head** right
* \-- \ top half of filled **arrow\_head** right
* \-- / bottom half of filled **arrow\_head** right
* \-- \\\ top half of open arrow\_head right
* \-- // bottom half of open **arrow\_head** right
* < -- filled **arrow\_head** left
* << -- open **arrow\_head** left
* / -- top half of filled **arrow\_head** left
* \ -- bottom half of filled **arrow head** left
* // -- top half of open **arrow\_head** left
* \\\ -- bottom half of open **arrow\_head** left
* \-- X object deletion message
* < -- > bidirectional arrows are possible with all **arrow\_heads**

#### Example: Arrow Heads

```
@startuml
'Example: Messages Arrow Head

Sean  -->   Maria : -->
Sean  -->>  Maria : -->>
Sean  --\   Maria : --\\
Sean  --/   Maria : --/
Sean  --\\  Maria : --\\\\
Sean  --//  Maria : --//
Maria <--   Zarek : <--
Maria <<--  Zarek : <<--
Maria /--   Zarek : /--
Maria \--   Zarek : \--
Maria //--  Zarek : //--
Maria \\--  Zarek : \\--
Maria --X   Zarek : --X
Sean  <-->  Zarek : <-->

@enduml
```

![Arrow Heads](<../../../../.gitbook/assets/Messages06\_arrow\_head (1).png>)

### Message Text

Place **message\_text** at the end of the message after a colon. You can format **message\_text** with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. Use **\n** for manual line breaks. For automatic line breaks see **maxMessageSize** in the [Skin Parameters](../skin-parameters.md) section. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

```
@startuml
'Example: Message Text

'Send a message from Sean to Maria with a bold message.
'Use creole.
Sean  ->  Maria : **Text**

'Send a reply to Sean with purple text.
'Use markup. 
Sean  <-- Maria : <color #561D5E>Text</color>

'Send a message from Maria to Zarek with stricken purple text.
'Use creole for bold and markup for the color.
Maria ->  Zarek : <color #561D5E>--Text--</color>

'Send a reply to Maria with a bold red message.
'Use only markup.
Maria <-- Zarek : <b><color:#FF0000>Text</color></b>

'Send a multiline message from Zarek to Sean.
Zarek ->  Sean : Multiline \nText

@enduml
```

![Message Text](../../../../.gitbook/assets/Messages07\_message\_text.png)
