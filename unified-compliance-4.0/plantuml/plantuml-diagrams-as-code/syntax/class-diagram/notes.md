# Notes

Notes give you the ability to digitally stick notes onto your class diagram.

## Declaration

Notes are declared with the command word **note**. They require an **anchor** and an **orientation** from that anchor.

#### Example: Note Declaration

```
@startuml
'Example: Note Declaration

'Create two classes with methods and properties.
class Class1 {
  Method_1()
  Property_1
}

class Class2 {
  Method_2()
  Property_2
}

'Create a relationship between the two classes.
Class1 -> Class2 : A Relationship

'Create a note.
note left of Class1 : A Note

@enduml
```

![Note Declaration](../../../../.gitbook/assets/Notes01\_declaration.png)

## Properties

* **orientation** - the direction the note appears in relation to the **anchor**
* **anchor** - the entity that determines the location of the note
* **fill\_color** - the color of the note
* **text** - the message of the note

### Orientation

Orientation determines the direction the note is positioned in relation to the anchor. The eight options are below.

* **left of** - orients a note to the left of the named **anchor**
* **right of** - orients a note to the right of the named **anchor**
* **top of** - orients a note to the top of the named **anchor**
* **bottom of** - orients a note to the bottom of the named **anchor**
* **left** - orients a note to the left of the most recently declared class
* **right** - orients a note to the right of the most recently declared class
* **top** - orients a note to the top of the most recently declared class
* **bottom** - orients a note to the bottom of the most recently declared class
* &#x20;**\* on link** - orients note to the most recently defined relationship, \* can be left out or be replaced with **left**, **right**, **top**, or **bottom**.

#### Example: Note Orientation

```
@startuml
'Example: Note Orientation

'Create a class with a method and property.
class Class1 {
  Method_1()
  Property_1
}

'Create a note to the left of the previous class.
note left : A Note

'Create a second class with a method and property.
class Class2 {
  Method_2()
  Property_2
}

'Create a relationship between the two classes.
Class1 -> Class2 : A Relationship

'Create a note above the previous relationship.
note top on link : Another Note

'Create a note below Class2.
note bottom of Class2 : Yet Another Note

@enduml
```

![Note Orientation](<../../../../.gitbook/assets/Notes02\_orientation (1).png>)

### Anchor

Anchors determine where a notes orientation originates. Anchors can be classes, relationships, or any class members such as attributes and methods.&#x20;

If the anchor is a class member you can only use left and right orientations. If a method occurs more than once in a class, you must specify the desired method with the values inside of the parentheses. You must also use the multiline text option with the **end note** command. Multiline texts will be explained further in the **text** property.

#### Example: Note Anchors

```
@startuml
'Example: Note Anchors

'Create a class with a method and property.
class Class1 {
  Method_1(args0)
  Property_1
}

'Create a second class with a method and property.
'Repeat the property with a different value in the parentheses.
class Class2 {
  Method_2(args0)
  Method_2(args1)
  Property_2
}

'Create a relationship between the two classes.
Class1 --> Class2 : A Relationship

'Create a note to the left of Method_1.
note left of Class1::Method_1
  A Note
end note

'Create a note on the previous relationship.
note on link : Another Note

'Create two notes to the right of both Method_2() methods.
note right of Class2::Method_2(args0)
  args0 Note
end note

note right of Class2::Method_2(args1)
  args1 Note
end note

@enduml
```

![Note Anchors](<../../../../.gitbook/assets/Notes03\_anchors (1).png>)

### Fill Color

The **color** property is the only optional property. It can be defined with one color or can be defined with two colors to make a gradient. You can define colors with a standard color name or hex code. There is always a **#** before the color name or hex code. Create a gradient by using two colors.

Note: At the time of this writing **fill\_color** is not supported on notes whose anchors are members.

#### Example: Note Fill Colors

```
@startuml
'Example: Note Fill Colors

'Create a class with a method and property.
class Class1 {
  Method_1(args0)
  Property_1
}

'Create a second class with a method and property.
'Repeat the property with a different value in the parentheses.
class Class2 {
  Method_2(args0)
  Method_2(args1)
  Property_2
}

'Create a relationship between the two classes.
Class1 --> Class2 : A Relationship

'Create a note to the left of Class1 with a color.
note left of Class1 #E6E6E7/561D5E : A Note

'Create a note on the previous relationship with a color.
note on link #CD1E1E
  Another Note
end note

@enduml
```

![Note Fill Colors](../../../../.gitbook/assets/Notes04\_fill\_color.png)

### Text

The **text** property provides the text that is displayed in the note. This is also where the **text** is formatted. Attached note **text** supports creole for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with the **end note** command. For multiline text remove the **:** and begin the **text** on the line below the **note** command. You can use as many lines as necessary. End the note on the last line with the **end note** command. Empty lines will be displayed on the note.

#### Example: Note Text

```
@startuml
'Example: Note Text

'Create a class with a method and property.
class Class1 {
  Method_1(args0)
  Property_1
}

'Create a second class with a method and property.
'Repeat the property with a different value in the parentheses.
class Class2 {
  Method_2(args0)
  Method_2(args1)
  Property_2
}

'Create a relationship between the two classes.
Class1 --> Class2 : A Relationship

'Create a note to the left of Class1.
'Use creole for text emphasis.
note left of Class1 : **A Note**

'Create a multiline note on the previous relationship.
'Use markup for color and emphasis.
note on link 
  <color #576065>Another</color>
  <i>Note</i>
end note

@enduml
```

![Note Text](<../../../../.gitbook/assets/Notes05\_text (1) (1).png>)

### With All Properties

#### Example: Notes With All Properties

```
@startuml
'Example: Notes With All Properties

class Class1 {
  Method_1(args0)
  Property_1
}

class Class2 {
  Method_2(args0)
  Method_2(args1)
  Property_2
}

Class1 --> Class2 : A Relationship

note left of Class1 #CD1E1E: **A Note**

note on link #561D5E/191C1F
  <color #E6E6E7>Another</color>
  <color #E6E6E7><i>Note</i></color>
end note

@enduml
```

![Notes With All Properties](<../../../../.gitbook/assets/Notes06\_all\_properties (1).png>)



## Attached Notes

Attached notes have an **alias** instead of a **position**. **** The position is determined by the entities the note is attached to. Attached notes contain three properties. The **alias** comes last if the **text** is on one line. If you use multiline **text** with **end note**, the alias comes immediately after the command word **note**. Notes with aliases that are not attached to anything will appear on their own in the diagram.

* **text** - the text that appears on the note
* **alias** - allows other entities to connect to the attached notes
* **fill\_color** - determines the background color of the note

### Text

The **text** property provides the text that is displayed in the note. This is also where the **text** is formatted. Attached note **text** supports creole for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The **#** is optional for hex codes in this portion of markup. It appears to be optional in all \<color> tags as well.&#x20;

Multiline text can be achieved with the **end note** command. For multiline text remove the **:** and begin the **text** on the line below the **note** command. You can use as many lines as necessary. End the note on the last line with the **end note** command. Empty lines will be displayed on the note.

### Alias

The **alias** allows the note to be attached to any other entity on the diagram. The **alias** comes last if the **text** is on one line. If you use multiline **text** with **end note**, the alias comes immediately after the command word **note**.&#x20;

#### Example: Attached Note With Alias and Text

```
@startuml
'Example: Attached Notes

'Create a class with a method and property.
class Class1 {
  Method_1(args0)
  Property_1
}

'Create a second class with a method and property.
'Repeat the property with a different value in the parentheses.
class Class2 {
  Method_2(args0)
  Method_2(args1)
  Property_2
}

'Create a relationship between the two classes.
Class1 --> Class2 : A Relationship

'Make a note with an alias.
'Add color and emphasis.
note "<color #561D5E>Note <b>Text</b></color>" as noteAlias_1

'Make a multiple line note with an alias.
note as noteAlias_2
Multiline
Unattached
Note
end note

'Attach the first note to both classes.
Class1 .. noteAlias_1
Class2 .. noteAlias_1

@enduml
```

![Attached Notes](<../../../../.gitbook/assets/Notes07\_attached\_notes (1).png>)

### Fill Color

**Fill\_color** is the only optional property. Place the **fill\_color** on the same line immediately after the alias. It can be defined with one color or can be defined with two colors to make a gradient. You can define colors with a standard color name or hex code. There is always a **#** before the color name or hex code.

#### Example: Attached Notes Color

```
@startuml
'Example: Attached Notes Color

'Create a class with a method and property.
class Class1 {
  Method_1(args0)
  Property_1
}

'Create a second class with a method and property.
'Repeat the property with a different value in the parentheses.
class Class2 {
  Method_2(args0)
  Method_2(args1)
  Property_2
}

'Create a relationship between the two classes.
Class1 --> Class2 : A Relationship

'Make a note with an alias.
'Add a fill color.
note "A Note" as noteAlias_1 #CD1E1E

'Make a multiple line note with an alias.
'Add a fill color.
note as noteAlias_2 #561D5E/E6E6E7
Multiline
Unattached
Note
end note

'Attach the first note to both classes.
Class1 .. noteAlias_1
Class2 .. noteAlias_1

@enduml
```

![Attached Notes Color](<../../../../.gitbook/assets/Notes08\_attached\_notes\_color (1).png>)
