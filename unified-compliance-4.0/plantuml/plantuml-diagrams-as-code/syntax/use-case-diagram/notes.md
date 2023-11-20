# Notes

Notes give you the ability to digitally stick notes onto your use case diagram.

## Declaration

Notes are declared with the command word **note**.&#x20;

#### Example: Note Declaration

```
@startuml
'Example: Note Declaration

'Create an actor and a use_case.
:Zarek:
(Stock)

'Create an association between the actor and use_case.
Zarek -- Stock

'Create a note to the right of the actor.
note right of Zarek: Note Text

@enduml
```

![Note Declaration](<../../../../.gitbook/assets/Notes01\_declaration (1).png>)

## Properties

Sequence diagram notes contain three properties.

* **position** - determines the location of the note
* **color** - determines the background color of the note
* **text** - the text that appears on the note

### Position

There are four options for the **position** property. They must be followed by the **use case description** or **actor name**. If either has an **alias**, use the **alias**.&#x20;

* **right of** - appears to the right of the named entity
* **left of** - appears to the left of the named entity
* **top of** - appears to the top of the named entity
* **bottom of** - appears to the bottom of the named entity

#### Example: Note Position

```
'Example: Note Position

'Create an actor.
:Zarek:

'Create a note to the right of the actor.
note right of Zarek: Right

'Create a note above the actor.
note top of Zarek: Top

'Create a note to the left of the actor.
note left of Zarek: Left

'Create a note below the actor.
note bottom of Zarek: Bottom

@enduml
```

![Note Position](../../../../.gitbook/assets/Notes02\_position.png)

### Color

The **color** property is the only optional property. It can be defined with one color or can be defined with two colors to make a gradient. You can define colors with a standard color name or hex code. There is always a **#** before the color name or hex code.

#### Example: Note Color

```
@startuml
'Example: Note Color

'Create an actor.
:Zarek:

'Create a note to the left of the actor.
'Add a color.
note left of Zarek #Red : Note

'Create a note to the right of the actor.
'Add a gradient color.
note right of Zarek #561D5E/FF0000 : Note

@enduml
```

![Note Color](../../../../.gitbook/assets/Notes03\_color.png)

### Text

The **text** property provides the text that is displayed in the note. This is also where the **text** is formatted. Attached note **text** supports markup language for color and emphasis. You can define colors with a standard color name or hex code. The **text** property does not support bold, italics, or monospace in markup. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with the **end note** command. For multiline text remove the **:** and begin the **text** on the line below the **note** command. You can use as many lines as necessary. End the note on the last line with the **end note** command. Empty lines will be displayed on the note.

#### Example: Note Text

```
@startuml
'Example: Note Text

'Create an actor.
:Zarek:

'Make a note to the left of the actor.
'Add color and emphasis.
note left of Zarek: <color #561D5E>Note <b>Text</b></color>

'Make a note with multiple lines of text to the right of the actor.
'Leave one empty line.
note right of Zarek
Multiline

Note
Text
end note

@enduml
```

![Note Text](../../../../.gitbook/assets/Notes04\_text.png)

## Attached Notes

Attached notes have an **alias** instead of a **position**. **** The position is determined by the entities the note is attached to.&#x20;

## Properties



Attached notes contain three properties. The **alias** comes last if the **text** is on one line. If you use multiline **text** with **end note**, the alias comes immediately after the command word **note**.

* **text** - the text that appears on the note
* **alias** - allows other entities to connect to the attached notes
* **color** - determines the background color of the note

### Text

The **text** property provides the text that is displayed in the note. This is also where the **text** is formatted. Attached note **text** supports markup language for color and emphasis. You can define colors with a standard color name or hex code. The **text** property does not support bold, italics, or monospace in markup. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with the **end note** command. For multiline text remove the **:** and begin the **text** on the line below the **note** command. You can use as many lines as necessary. End the note on the last line with the **end note** command. Empty lines will be displayed on the note.

### Alias

The **alias** allows the note to be attached to any other entity on the diagram. The **alias** comes last if the **text** is on one line. If you use multiline **text** with **end note**, the alias comes immediately after the command word **note**.

#### Example: Attached Note With Alias and Text

```
@startuml
'Example: Attached Note With Alias and Text

'Create three actors.
:Zarek:
:Ivy:
:Sean:

'Make a note with an alias.
'Add color and emphasis.
note "<color #561D5E>Note <b>Text</b></color>" as noteAlias_1

'Make a multiple line note with an alias.
'Leave one empty line.
note as noteAlias_2
Multiline

Note
Text
end note

'Attach the first note to the first and second actors.
Zarek .. noteAlias_1
Ivy .. noteAlias_1

'Attach the second note to the second and third actors.
Ivy .. noteAlias_2
Sean .. noteAlias_2

@enduml
```

![Attached Note With Alias and Text](<../../../../.gitbook/assets/Notes05\_attached\_text (1).png>)

### Color

The **color** property is the only optional property. Place the **color** on the same line immediately after the alias. It can be defined with one color or can be defined with two colors to make a gradient. You can define colors with a standard color name or hex code. There is always a **#** before the color name or hex code.

#### Example: Attached Note With Color

```
@startuml
'Example: Note Text

'Create three actors.
:Zarek:
:Ivy:
:Sean:

'Make a note with an alias.
'Add a background color.
note "Text" as noteAlias_1 #Red

'Make a multiple line note with an alias.
'Leave one empty line.
'Add a background color gradient.
note as noteAlias_2 #561D5E/FF0000
Multiline

Note
Text
end note

'Attach the first note to the first and second actors.
Zarek .. noteAlias_1
Ivy .. noteAlias_1

'Attach the second note to the second and third actors.
Ivy .. noteAlias_2
Sean .. noteAlias_2

@enduml
```

![Attached Note With Color](../../../../.gitbook/assets/Notes07\_attached\_color.png)
