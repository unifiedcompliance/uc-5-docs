# ExecutionSpecification

ExecutionSpecifications are thin rectangles drawn along the lifeline that show the start and finish of an action that is being executed.&#x20;

## Commands

ExecutionSpecification uses the commands shown below.

* **activate** - starts drawing the occurrence of an ExecutionSpecification
* **deactivate** - finishes drawing the occurrence of an ExecutionSpecification
* **destroy** - destroys an instance of a given lifeline
* **autoactivate** - eases and automates the use of ExecutionSpecification&#x20;
* **return** - used with **autoactivate** to send reply messages and finish an ExecutionSpecification
* **++** - shortcut for activate
* **--** - shortcut for deactivate
* **!!** - shortcut for destroy

### Activate & Deactivate

The **activate** and **deactivate** commands are used to start and finish an ExecutionSpecification. The commands follow the message line where you want to affect the ExecutionSpecification.

#### Example: Activate & Deactivate

```
@startuml
'Example: Activate & Deactivate

participant Sean
participant Maria

'Start Sean's ExecutionSpecification.
[-> Sean
activate Sean

'Start Maria's ExecutionSpecification.
Sean -> Maria : Text
activate Maria

'Finish Maria's ExecutionSpecification.
Maria --> Sean
deactivate Maria

'Finish Sean's ExecutionSpecification.
[<--Sean
deactivate Sean

@enduml
```

![Activate & Deactivate](../../../../.gitbook/assets/ExecutionSpecification01\_activate\_deactivate.png)

### Destroy

The **destroy** command uses an "X" to signify that a lifeline will no longer be active. It will also automatically finish an ExecutionSpecification.

#### Example: Destroy

```
@startuml
'Example: Destroy

participant Sean
participant Maria
participant Zarek

'Start Sean's ExecutionSpecification.
[-> Sean
activate Sean

'Start Maria's ExecutionSpecification.
Sean -> Maria : Text
activate Maria

'Destroy Maria's ExecutionSpecification and start Zarek's
Maria -> Zarek
destroy Maria
activate Zarek

Zarek -> Sean
Sean --> Zarek

'Finish Zarek's ExecutionSpecification.
Zarek -> Sean
deactivate Zarek

'Finish Sean's ExecutionSpecification.
[<--Sean
deactivate Sean

@enduml
```

![Destroy](<../../../../.gitbook/assets/ExecutionSpecification02\_destroy (1).png>)

### Autoactivate & Return

If you set the **autoactivate** command to "true" PlantUML will automatically start ExecutionSpecifications a when a lifeline is active. In order to properly deactivate auto-activated lifelines the **return** command must be used. The **return** command deactivates the most recent lifeline that is still active and sends the reply message to that lifeline's activator. The format and color of return messages will be covered in the [Messages](messages.md) chapter of this book.

**Example: Autoactivate & Return**

```
@startuml
'Example: Autoactivate & Return

'This activates automatic lifeline generation
autoactivate on

'Sean's primary ExecutionSpecification with 
'a gate sending the message as the activator.
[-> Sean : A gate activates Sean

'Start Maria's ExecutionSpecification with Sean as the activator.
Sean -> Maria : Sean activates Maria

'Start Zarek's ExecutionSpecification with Maria as the activator.
Maria -> Zarek : Maria activates Zarek

'Finish Zarek's ExecutionSpecification while replying to Maria.
return Zarek replies to Maria

'Finish Maria's ExecutionSpecification while replying to Sean.
return Maria replies to Sean.

'Finish Sean's ExecutionSpecification while replying to the gate.
return Sean replies to the gate

@enduml
```

![Autoactivate & Return](../../../../.gitbook/assets/ExecutionSpecification03\_autoactivate\_return.png)

### Shortcuts

The below shortcuts are for starting, finishing, and destroying ExecutionSpecifications with less code. When using these shortcuts you can start and finish ExecutionSpecifications on the same line. See line 15. Compare the **destroy** example above to the similar example below. At the time of this writing there is no short cut for destroying a source as is done in the **destroy** example on line 18. The **!!** command will only destroy a message target.

#### Example: ExecutionSpecification Shortcuts

```
@startuml
'Example: ExecutionSpecification Shortcuts

participant Sean
participant Maria
participant Zarek

'Start Sean's ExecutionSpecification.
[-> Sean ++ :Text

'Start Maria's ExecutionSpecification.
Sean -> Maria ++ : Text

'Finish Maria's ExecutionSpecification and start Zarek's
Maria -> Zarek --++ : Text

Zarek -> Sean

'Destroy Zarek's ExecutionSpecification.
Sean --> Zarek !! : Text

'Finish Sean's ExecutionSpecification.
[<-- Sean -- : Text

@enduml
```

![Shortcuts](../../../../.gitbook/assets/ExecutionSpecification04\_shortcuts.png)

## Color

ExecutionSpecifications only have one property, **color**. You can define colors with a standard color name or hex code. This works with all of the commands that start an ExecutionSpecification. However the syntax varies. When using the commands **activate** or **autoactivate,** place the **color** immediately after the activated lifeline name. When using **++**, place the **color** after right after the **++**.

#### Example: ExecutionSpecification Color

```
@startuml
'Example: ExecutionSpecification Color

participant Sean
participant Maria
participant Zarek

'Start an ExecutionSpecification for Sean that is cyan.
'Use the shortcut method.
[-> Sean ++ #cyan: Text

'Start an ExecutionSpecification for Maria that has a gradient.
'Use the activate method and make the color purple.
Sean -> Maria : Text
activate Maria #561D5E

'Start an ExecutionSpecification for Zarek that is red.
'Use autoactivate.
autoactivate on
Maria -> Zarek #FF0000: Text

return Text
return Text
return Text

@enduml
```

![ExecutionSpecification Color](../../../../.gitbook/assets/ExecutionSpecification05\_color.png)

## Nesting

You can nest ExecutionSpecifications by activating a lifeline while it still has an active ExecutionSpecification.

#### Example: ExecutionSpecification Nesting

```
@startuml
'Example: ExecutionSpecification Nesting

participant Sean
participant Zarek

'Start Sean's primary ExecutionSpecification
[-> Sean : Text
activate Sean

'Start Sean's secondary ExecutionSpecification
Sean -> Sean : Internal Text
activate Sean

'Start Zarek's ExecutionSpecification.
Sean -> Zarek : Text
activate Zarek

'Finish Zarek's ExecutionSpecification.
'Finish Sean's secondary ExecutionSpecification
Zarek --> Sean : Text
deactivate Zarek
deactivate Sean

'Finish Sean's primary ExecutionSpecification
[<-- Sean : Text
deactivate Sean

@enduml
```

![ExecutionSpecification Nesting](../../../../.gitbook/assets/ExecutionSpecification06\_nesting.png)

## Object Deletion Message
