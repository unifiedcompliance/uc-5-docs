# Notes

Notes are exactly that. They give you the ability to digitally stick notes onto your diagram.

## Declaration

Notes are declared with one of three words. These words also determine the shape of the note. This blurs the line between command word and property. It is easier to explain as a property and is explained further in the **shape** property below. The basic keyword is **note**.

#### Example: Note Declaration

```
@startuml
'Example: Note Declaration

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Make a basic note.
note across : Note Text

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Note Declaration](<../../../../.gitbook/assets/Notes01\_declaration (1) (1).png>)

## Properties

Sequence diagram notes contain four properties. The **shape**, **position**, and **text** properties are required.&#x20;

* **shape** - determines the shape of the note
* **position** - determines the location of the note
* **color** - determines the background color of the note
* **text** - the text that appears on the note

### Shape

The **shape** property allows for three shapes. It is required.

* **note** - a note in the shape of a rectangle with the corner folded
* **rnote** - a note in the shape of a rectangle with no folds
* **hnote** - a note in the shape of a hexagon

#### Example: Note Shape

```
@startuml
'Example: Note Shape

'Make a standard shape note.
note across : Note Text

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Make a rectangle shape note.
rnote across : Note Text

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Make a hexagon shape note.
hnote across : Note Text

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Note Shape](../../../../.gitbook/assets/Notes02\_shape.png)

### Position

There are six options for the **position** property. The first three must be followed by the **name** or **formatted\_name** of a lifeline. The over property can be followed by one or two names separated by a comma. The first four options display the note below the previous message. If a note is declared before any messages it will appear just below the lifeline **head**.

* **right of** - appears to the right of the named lifeline and below the previous message
* **left of** -appears to the left of the named lifeline and below the previous message
* **over** - appears over the named lifeline or lifelines and below the previous message
* **across** - appears over all lifelines and below the previous message
* **right** - appears to the right of the previous message
* **left** - appears to the left of the previous message

#### Example: Note Position

```
@startuml
'Example: Note Position

'Make a note to the right of Sean
note right of Sean : Note Text

'Send a message from Sean to Maria.
Sean  ->  Maria : Message Text

'Make a note to the left of Maria.
note left of Maria : Note Text

'Send a reply from Maria to Sean.
Sean  <-- Maria : Message Text

'Make a note over Sean and Maria.
note over Sean, Maria : Note Text

'Make a note over Zarek.
note over Zarek : Note Text

'Make a not across all liflines.
note across : Note Text

'Send a message from Zarek to Sean.
Zarek ->  Sean : Message Text

'Make a note to the right of the above message.
note right : Note Text

'Send a reply from Sean to Zarek.
Zarek <-- Sean : Message Text

'Make a note to the left of the above message.
note left : Note Text

@enduml
```

![Note Position](../../../../.gitbook/assets/Notes03\_position.png)

### Color

The **color** property is the only optional property. It can be defined with one color or can be defined with two colors to make a gradient. You can define colors with a standard color name or hex code. There is always a **#** before the color name or hex code.

#### Example: Note Color

```
@startuml
'Example: Note Color

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Message Text
Sean  <-- Maria : Message Text

'Make a note with a cyan background.
note over Sean #cyan : Note Text

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Message Text
Maria <-- Zarek : Message Text

'Make a note with a gradient background of purple and red.
hnote over Maria, Zarek #561D5E/FF0000 : Note Text

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Message Text
Zarek <-- Sean : Message Text

@enduml
```

![Note Color](../../../../.gitbook/assets/Notes04\_color.png)

### Text

The **text** property provides the text that is displayed in the note. This is also where the **text** is formatted. Note **text** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The **text** property does not support bold, italics, or monospace in markup. You must use creole for these. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with the **end note** command. For multiline text remove the : and begin the **text** on the line below the **shape** property. You can use as many lines as necessary. End the note on the last line with the **end note** command. Empty lines will be displayed on the note.

#### Example: Note Text

```
@startuml
'Example: Note Text

'Make a note with bold text. Use creole.
note over Sean : **Note Text**

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Message Text
Sean  <-- Maria : Message Text

'Make a note with purple text. Use markup.
hnote over Maria, Zarek : <color #561D5E>Note Text</color>

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Message Text
Maria <-- Zarek : Message Text

'Make a note with bold red text.
rnote over Maria, Zarek : <color FF0000>**Note Text**</color>

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Message Text
Zarek <-- Sean : Message Text

'Make a note with multiple lines of text.
'Leave one empty line.
note across
Multiline

Note
Text
end note

@enduml
```

![Note Text](<../../../../.gitbook/assets/Notes05\_text (1).png>)

## Images In Notes

You can place images in note **text** with the **\<img>** markup tag. You can adjust the size of the image with the **{scale}** property.

#### Example: Note Images

```
@startuml
'Example: Note Images

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Message Text
Sean  <-- Maria : Message Text

'Make a note with an image in it.
note across
This note has an image 
<img:https://www.unifiedcompliance.com/wp-content/themes/tardigrade//images/cch_logo_icon.png>
end note

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Message Text
Maria <-- Zarek : Message Text

'Make another note with the same image.
'Change the size of the image.
note across
This note has a smaller image
<img:https://www.unifiedcompliance.com/wp-content/themes/tardigrade//images/cch_logo_icon.png{scale=0.5}>
end note

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Message Text
Zarek <-- Sean : Message Text

@enduml
```

![Note Images](../../../../.gitbook/assets/Notes06\_images.png)

## Note Alignment

You can place multiple notes on the same level by placing a **/** in front of all but the first note. Alignment only works with the **left of**, **right of**, and **over** positions. And, you can only refer to a specific **lifeline** once when placing notes at the same level. For example you cannot use **left of** Sean and **over** Sean in the same alignment.

#### Example: Note Alignment

```
@startuml
'Example: Note Alignment

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Message Text
Sean  <-- Maria : Message Text

'Make notes over Sean and Maria.
'Align them at the same level.
hnote over Sean: Message Text
/ hnote over Maria: Message Text

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Message Text
Maria <-- Zarek : Message Text

'Make three notes.
'Align them at the same level.
note left of Sean: Message Text
/ note left of Maria: Message Text
/ note over Zarek: Message Text

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Message Text
Zarek <-- Sean : Message Text

@enduml
```

![Note Alignment](../../../../.gitbook/assets/Notes07\_aligned.png)
