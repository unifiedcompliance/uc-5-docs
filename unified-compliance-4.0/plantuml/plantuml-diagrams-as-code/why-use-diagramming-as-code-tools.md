# Why use diagramming as code tools?



The list of software tools for creating UML diagrams is **huge**, too huge to list here (just search “uml software” and you’ll see). Many of those tools are great, but in reality, many of them are also complex. This gives us reason #1 for why you shouldn’t use them, along with the second reason:

1. **Complexity** - Each tool has its own interface, its own way of creating the diagrams we need to share. Therefore, each time we use a new tool, _we have to learn that tool’s interface_. There isn’t ever going to be a time where any of these tools becomes the “Microsoft Word or Excel or PowerPoint” of UML diagramming. They aren’t going to be ubiquitous enough to become a standard.
2. **Shareable Output** - While all output in PNG, JPeG, and SVG, none of them output in XML or JSON-LD following a single standard. There isn’t a UML standard at schema.org, and there’s no XML version _of_ a schema.org. So while all of these applications can output to a _format_ standard, they don’t output to a _shareable, editable_ standard.

## Overcoming complexity

Diagramming using text is pretty darned simple. Any of the diagram as code tools have a very low barrier to entry. The fact that UML models are stored as text simplifies their integration with a variety of tools (like version control systems) that we in the compliance and IT fields already use in our everyday work, so there’s no need to learn/buy/install additional tools.

_What if_ you could use **text** and a few snippets of formatting around that text, to turn that text into various forms of diagramming? What if we wanted to visualize something as simple as

> _This_ communicates with _That_

In order to visualize this in PlantUML, you simply need a few pointers and the type of diagram you want to draw.

The only difference, we’ve found so far, is in the language used. Yuml.me, code2flow.com, and a few others (listed above as not interchangeable) use a non-standard version of the text-based syntax.

### Quick intro of the syntax

The basic syntax is insanely easy to understand. We’ll go through the top levels of the syntax and show you.

#### Opening and Closing Arguments

Everything starts and ends with an argument. For most everything, you’ll use a start/end uml statement. For taking raw JSON or YAML its start/end json or yaml as appropriate.

```
@startuml

Content goes here

@enduml
```

Here are the types of diagrams you can create, showing both their text and the auto-generated graphics that go with them.

**Activity**

An Activity diagram is basically a flowchart to represent the flow from one activity to another activity.

```
@startuml
:This;
:That;
@enduml
```



![Activity](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-activity.png)

Everything begins and ends with @xxxuml. In between, there isn’t much difference in the _text_ of what is added, only the formatting. In the sequence diagram that follows, we add the communication text and slightly reformat how _This_ and _That_ are written.

**Sequence**

Sequence diagrams illustrate how messages flow through a system, also known as event diagrams. It enables the visualization of several dynamic scenarios. There is a sequential sequence of events that occurs between two lifelines, meaning both lifelines are present at the same time. According to UML, there is an upper and lower lifeline and a message flow represented by three vertical dotted lines at the bottom of the page.

```
@startuml
This -> That : Communication
@enduml
```



![Sequence](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-sequence.png)

Again, for the Use Case diagram, we simply re-format how _This_ and _That_ are written.

**Use Case**

The use case diagram illustrates how the system’s users interact with it. An application, system, or process that interacts with people, organizations, or external systems may benefit from the development of a use case diagram.

```
@startuml
:This: -> :That: : Communication
@enduml
```



![Use Case](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-UseCase.png)

You should get the idea. Here are several other methods that can be used:

**Class**

The class diagram enables the conceptualization of application structure and the implementation of details in programming code. It is also possible to use class diagrams for data modeling.

```
@startuml
This -|> That: Communication
@enduml
```



![Class](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-Class.png)

#### Component

Component diagrams represent the different parts of a UML diagram. In contrast to describing the system’s functionality, it represents the components used to achieve that functionality.

```
@startuml
[This] -> [That]: Communication
@enduml
```

![Component](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-component.png)

**Deployment**

Deployment diagrams are a kind of structure diagram used in modeling the physical aspects of an object-oriented system. They are often be used to model the static deployment view of a system (topology of the hardware).

```
@startuml
folder This
file That
This -> That: Communication
@enduml
```



![Deployment](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-deployment.png)

And there are other, slightly different formats, that can be used as well.

**Work Breakdown Structure**

A work breakdown structure defines all the things a project needs to accomplish, organized into multiple levels, and displayed graphically.

```
@startwbs
+ This
++ That
+++ A sub-task
++ Some other Thing
@endwbs
```



![WBS](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-WBS.png)

As you can see, PlantUML allows users to specify various types of diagrams in a simple text format similar to programming languages. It is the most popular text format for diagramming. As we showed above, it supports many different diagram types, separates each diagram element according to its function, and uses a simple, human-readable language.

If you want to get fancy, you can use things like declaratives and other drawing tools.

#### Declaratives

Declaratives give you an order of display in many of your diagrams, like sequence diagrams. They also use keywords to draw specific shapes, such as actor, boundary, etc.

```
@startuml
participant Participant as Foo
actor       Actor       as Foo1
boundary    Boundary    as Foo2
control     Control     as Foo3
entity      Entity      as Foo4
database    Database    as Foo5
collections Collections as Foo6
queue       Queue       as Foo7
@enduml
```

The above text draws the following declarative diagram:

![Declaratives](https://www.complianceascode.net/wp-content/uploads/2021/12/declaratives.png)

#### Sequences

Adding sequences to such a diagram is then very simple. To create a sequence, you just add an solid lie arrow (“->”) or a dotted line arrow (“-->”)…

```
@startuml
participant Participant as Foo
actor       Actor       as Foo1
boundary    Boundary    as Foo2
control     Control     as Foo3
entity      Entity      as Foo4
database    Database    as Foo5
collections Collections as Foo6
queue       Queue       as Foo7
Foo -> Foo1 : To actor 
Foo -> Foo2 : To boundary
Foo -> Foo3 : To control
Foo --> Foo4 : To entity
Foo -> Foo5 : To database
Foo --> Foo6 : To collections
Foo -> Foo7: To queue
@enduml
```

…to create a sequence diagram like the one below:

![Full diagram](https://www.complianceascode.net/wp-content/uploads/2021/12/declarativefoo2.png)

#### Other

From there, the syntax also allows for _loops, text alignment, sequence numbering, etc._

The point in all of this is that the syntax is very easy to use, very easy to understand, and makes the diagrams very easy to share.

## The uses of Diagrams as Code in compliance

What types of diagrams as code can you create that apply to compliance? Pretty much everything you need to create:

![UML 2.5 Diagrams](https://www.complianceascode.net/wp-content/uploads/2021/12/UMv25Diagrams.png)

While compliance policies (both internal and external) are typically very well-defined, documentation on how exactly to carry out those policies effectively is not always well-defined or available. Creating detailed flow charts or workflows can be extremely advantageous to a corporate compliance department. Compliance workflows such as flow charts, ERDs, Sequence Diagrams, Dataflow Diagrams, etc., display the granular steps that need to be taken to ensure that the organization is in line with the internal controls set forth by management as well as the external obligations called for by governing bodies.

The following areas can benefit from the use of flow charts and workflows in order to promote comprehensive compliance throughout the company:

### Technical Structures

Technical structures, such as network diagrams (both simple and complex) can be created within UML.

An example of a simple network diagram is here:

![Simple Network Diagram](https://www.complianceascode.net/wp-content/uploads/2021/12/networkdiagram.png)

With a more complex diagram here:

![Complex Network Diagram](https://www.complianceascode.net/wp-content/uploads/2021/12/networkdiagram2.png)

And a deployment diagram here:

![Kubernetes deployment](https://www.complianceascode.net/wp-content/uploads/2021/12/Kubernetes.png)

### Dataflow Diagrams

Straight out of the FFIEC Operations Handbook,

> Management should develop data flow diagrams to supplement its understanding of information flow within and between network segments as well as across the institution’s perimeter to external parties.

That term, _data flow_ (also spelled _dataflow_ in the same documents), in combination with “maps”, “charts” and “analysis”, appears 15 times in 5 different Handbooks; Development and Acquisition, Information Security, Operations, Retail Payment Systems, and Wholesale Payment Systems.

Here’s a sample that was used in an actual PCI audit:

![Compliance-Related DFD](https://www.complianceascode.net/wp-content/uploads/2021/12/DataFlow.png)

**Each** of the diagrams above was created by **entering text** into the UML editor, automatically creating the graphical version.

### Policy Creation

Developing a standardized process and flow chart for policy creation can help to ensure speedy implementation of new corporate guidelines and minimize the amount of time new policies spend behind red tape.

### Policy Enforcement

Creating workflows, or flow charts, for the policy enforcement process can provide a number of benefits to the organization: decrease of issue resolution times and case backlog, decrease in compliance expenses and increase of trust from employees and shareholders. Step-by-step analysis and governance of the policy enforcement process will benefit employee relations, improve issue resolution operations and boost overall compliance efficiency.

An example of a policy enforcement workflow is the following Credit Card fraud resolution workflow:

```
@startuml
autonumber

actor Caller as caller
boundary "Org System" as Org
actor Specialist as specialist
control System as system
actor "Escalation Team" as team

group Inbound Call Processing
 caller -> system: begins fraud process
 system -> specialist: forward call
 specialist -> specialist: screens calls
 system -> specialist: populate screen with client profile
 specialist <-> caller: determines call is about 
 specialist -> caller: reads disclosure
 caller -> specialist: responds at checkpoints
end

group Issue REsolution & Case Creation
group Issue Process Determiniation

specialist -> specialist: Can I process this?
group Specialist must Escalate
specialist -> system: Enter notes
specialist -> system: transfer to Escalation Team
autonumber 10
specialist -> caller: transfer to Escalation Team
autonumber 10
system -> team: forward case
team -> team: review call recording
team <-> caller: Processes case
end

specialist -> caller: Review transactons

group Transactions Verified
specialist -> specialist: Review notes, determine cancellation

group Keep card open
specialist -> system: Reopen card & update data
specialist <-> caller: Anything else?
specialist -> system: Close file
end

group Close Card
specialist -> caller: Advise that the card must be closed
specialist -> caller: Inform caller a new card will be sent
specialist <-> caller: Dispute transaction?

group Dispute Transaction
specialist -> caller: Select transactions in dispute
specialist -> system: Enter dispute information
specialist -> caller: Provide claim information
specialist -> system: Enter notes

end
end
end
end

@enduml
```

Here’s how this looks as a diagram:

![Credit Card Policy Enforcement](https://www.complianceascode.net/wp-content/uploads/2021/12/ccenforcement.png)

### Regulatory Reporting

Documenting the regulatory reporting process is essential for the financial and reputational well-being of the company. Any missteps (unintentional or otherwise) in the regulatory reporting process can lead to penalties, fines, mistrust or excessive scrutiny from regulatory bodies in the future. Depicting regulatory reporting processes through flow charts can aid in guaranteeing that all necessary steps to report to regulatory bodies have been sufficiently completed.

### Risk Management

A risk management framework with process flows and checklists can help confirm that risks are not only identified, but also ranked, analyzed, responded to and monitored. A well-defined risk management function is able to measure and track the risks that have been identified throughout the process.

There are several methods for risk assessment during various phases of software development and at different levels of abstraction. However, there are very few techniques available for assessing risk at the requirements level and those that are available are highly subjective and are not based on any formal design models. Such techniques are human-intensive and highly error prone. However, using the Unified Modeling Language (UML) specifications of the software at the early development stages allows each requirement to be mapped to a specific operational scenario in UML.

There are several papers dedicated to using UML for risk assessment and risk management1. Because these diagrams can get quite complex, we aren’t going to show them here.

### Internal Audit

Since internal auditors’ main responsibility is to make sure corporate policies and processes are being adhered to, they too should have flow charts for their own auditing processes to make sure they are assessing and reporting the company’s operations properly.

## The Point of all of this…

The point of all of this is that **diagrams as code**, as **UML**, are quite acceptable forms of communication in the world of compliance.

### …is to create a federated library of UMLs!

And if that is the case, why don’t we _help each other out_ and create diagrams as code that others can use?

We all need to be compliant with this or that regulation. Many of those regulations call for data flow diagrams, network diagrams, risk management diagrams, etc. So _why reinvent the wheel_?

## References

1.  Alshareef, Hanaa, Sandro Stucki, and Gerardo Schneider. 2020. “Transforming Data Flow Diagrams for Privacy Compliance (Long Version).” ArXiv:2011.12028 \[Cs], November. [http://arxiv.org/abs/2011.12028](http://arxiv.org/abs/2011.12028) Accessed December 13, 2021.

    Braber, F, Theo Dimitrakos, Bjørn Gran, Ketil Stølen, and J Aagedal. 2002. “Model-Based Risk Management Using UML and RUP.” [https://www.researchgate.net/publication/30405101\_Model-based\_Risk\_Management\_using\_UML\_and\_RUP/link/0deec516c7b0f28feb000000/download](https://www.researchgate.net/publication/30405101\_Model-based\_Risk\_Management\_using\_UML\_and\_RUP/link/0deec516c7b0f28feb000000/download) Accessed December 13, 2021.

    K. Appukkutty, H.H. Ammar, K.G. Popstajanova. n.d. “Software REquirement Risk Assessment Using UML.” [https://community.wvu.edu/\~kagoseva/Papers/SRRAUUML.pdf](https://community.wvu.edu/\~kagoseva/Papers/SRRAUUML.pdf) Accessed December 13, 2021.

    “UML As a Tool for Modeling Risks.” n.d. Accessed December 13, 2021. [http://www.integrisk.eu-vri.eu/filedown.aspx?file=1685](http://www.integrisk.eu-vri.eu/filedown.aspx?file=1685). ↩︎
