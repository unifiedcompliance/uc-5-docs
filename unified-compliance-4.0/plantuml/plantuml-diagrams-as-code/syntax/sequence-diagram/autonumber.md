# Autonumber

You can assign your messages sequential numbers automatically with the **autonumber** command.

## Activation

Place the **autonumber** command in your code and the following messages will be numbered sequentially.

#### Example: Autonumber Activation

```
@startuml
'Example: Messages Autonumber

'Activate the autonumber method.
autonumber

'Send a few messages back and forth.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

Maria ->  Zarek : Text
Maria <-- Zarek : Text

Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Autonumber Activation](<../../../../.gitbook/assets/Autonumber01\_activation (1).png>)

## Commands

There are three commands that can follow **autonumber**. They are all optional. You will only need **resume** if you used **stop**, but it's not required. The **inc** command will be covered below in the [Specific Sequence](autonumber.md#specific-sequence) section.

* **stop -** does what is says on the box, stops the sequential numbering
* **resume** - resumes sequential numbering after using **stop**
* **inc** - adds specific increments to specific sequences

#### Example: Stop & Resume

```
@startuml
'Example: Autonumber Stop & Resume

'Activate the autonumber method.
autonumber

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Stop the autonumber method.
autonumber stop

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Resume the autonumber method.
autonumber resume

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Stop & Resume](../../../../.gitbook/assets/Autonumber02\_stop\_resume.png)

## Properties

All **autonumber** properties are optional. They must be used in order even if you don't use all properties. You must have a **start\_number** if you wish to use **increment**. The **format** property contains three optional parts. There is no mandatory order inside of **format**.

* **start\_number** - the initial number used in the **autonumber** sequence, comes after the **autonumber** command
* **increment** - the number added to the **autonumber** sequence with each message, comes after  **start\_number** or **resume**
* **format** - determines the format of the sequential numbers consist of three parts, the entire property must be inside of double quotes
  * **number\_format** - provides a format for the sequential numbers
  * **message** - displays a message with the sequential numbers
  * **text\_format** - similar to other formatting, usually surrounds the **message** and **number\_format**

### Start Number

The **start\_number** property immediately follows the **autonumber** command. It defines the number that will begin the numbering sequence. Note that it can not be used after the **resume** command.

#### Example: Start Number

```
@startuml
'Example: Autonumber Start Number

'Activate the autonumber method.
'Start the sequence at 10.
autonumber 10

'Send a few messages.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

Maria ->  Zarek : Text
Maria <-- Zarek : Text

Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Start Number](../../../../.gitbook/assets/Autonumber03\_start\_number.png)

### Increment

The **increment** property defines the size of the step between sequential numbers. It follows **start\_number** or **resume**. When combined with **resume** it will begin the new **increment** on the second message after the **resume** command.

#### Example: Increment

```
@startuml
'Example: Autonumber Increment

'Activate the autonumber method.
'Start the sequence at 5 with an increment of 5.
autonumber 5 5

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Stop the autonumber method.
autonumber stop

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Resume the autonumber method with an increment of 2
autonumber resume 2

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Increment](../../../../.gitbook/assets/Autonumber04\_increment.png)

#### Increment Option

If you want the sequential numbers in the above example to resume with an increment of two on the very next message, you will need to manually restart **autonumber**. Simply use the **autonumber** command with **start\_number** and **increment** again with the appropriate **start\_number**.

#### Example: Increment Option

```
@startuml
'Example: Autonumber Increment Option

'Activate the autonumber method.
'Start the sequence at 5 with an increment of 5.
autonumber 5 5

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Stop the autonumber method.
autonumber stop

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Manually resume the autonumber method with an increment of 2
autonumber 12 2

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Increment Option](../../../../.gitbook/assets/Autonumber05\_increment\_option.png)

### Number Format

The **number\_format** property determines if sequential numbers fill empty digits with zeroes or not. By using multiple zeroes you are telling the number\_format to keep zeroes as place holders in unused digits.

#### Example: Number Format

```
@startuml
'Example: Autonumber Number Format

'Activate the autonumber method with a start_number of 7.
'Reserve three digits for the sequential number.
autonumber 7 "000"

'Send several messages.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

Maria ->  Zarek : Text
Maria <-- Zarek : Text

Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Number Format](../../../../.gitbook/assets/Autonumber06\_number\_format.png)

### Message

The **message** property adds text to the sequential number. The **number\_format** or **#** character determine where the sequential number will appear in relation to the **message**.  Without an accompanying **number\_format** or **#** the **message** will appear to the left of the sequential number.&#x20;

#### Example: Autonumber Message

```
@startuml
'Example: Autonumber Message

'Activate the autonumber method.
'Add a message.
autonumber "Message Here "

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Start a new autonumber method.
'Reserve two digits and place the sequential number before a message.
autonumber "00 Message Here"

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Start a new autonumber method.
'Do not reserve any digits and place the sequential number inside a message.
autonumber "Message # Here"

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Autonumber Message](../../../../.gitbook/assets/Autonumber07\_message.png)

### Text Format

The **text\_format** can affect the sequential number and the **message**. You can alter **text\_format** with creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.&#x20;

#### Example: Text Format

```
@startuml
'Example: Autonumber Text Format

'Activate the autonumber method.
'Make the sequential number underlined with creole.
autonumber "__#__"

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Start a new autonumber method.
'Add a message and make it purple with markup.
autonumber "<font color=561D5E>Message Here </font>"

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Start a new autonumber method.
'Add a message and reserve three digits.
'Make it all bold and cyan with markup.
autonumber "<font color=cyan><b>Message Here 000 </b></font>"

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Text Format](../../../../.gitbook/assets/Autonumber08\_text\_format.png)

## Specific Sequence

You can build a specific sequence similar to version numbers with the **autonumber** method. By using any combination of four delimiters( **. , : ;** ). The specific sequence can be two or three digits. The specific sequence takes the place of the **start\_number**. By default the last digit will increment with each message. The **inc** command followed by the letters **A** or **B** allows you to manually increment the other digits. When **A** or **B** are incremented all digits to the right will automatically reset to one. Specific sequence does not support any **autonumber** **format** properties.

```
@startuml
'Example: Autonumber Specific Sequence

'Activate the autonumber method.
'Make a three digit specific sequence with two different delimiters.
autonumber 1;1:1

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Increase the second digit
autonumber inc B

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Start a new autonumber method.
''Make a three digit specific sequence with periods.
autonumber 1.1.1

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

'Increase the first digit
autonumber inc A

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

@enduml
```

![Specific Sequence](../../../../.gitbook/assets/Autonumber09\_specific\_sequence.png)

## As a Variable

You can use the variable **%autonumber%** anywhere in your sequence diagram after starting the **autonumber** method. It will display the current value of the sequential number. For more on notes see the [notes](notes.md) section.

#### Example: As a Variable

```
@startuml
'Example: Autonumber As a Variable

'Activate the autonumber method.
autonumber

'Send a message from Sean to Maria and a reply.
'Put the sequence number in the message_text.
'Make the message text cyan.
Sean  ->  Maria : <color:#cyan>Text %autonumber%</color>
Sean  <-- Maria : <color:#cyan>Text %autonumber%</color>

'Add a note with the autonumber value in the note.
note across : The current autonumber value is %autonumber%.

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

@enduml
```

![Autonumber as a Variable](../../../../.gitbook/assets/Autonumber10\_variable.png)
