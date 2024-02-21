# The uses of Diagrams as Code in compliance

An entire movement surrounds the concept of “Documentation as Code,”[^ “Documentation as Code”; “Using Code as Documentation to Save Time and Share Context”; “Bliki”; “Docs as Code”; “Diagrams as Code: A Paradigm Shift for Visual Communication.”] and diagrams as code fits _into_ that concept. Documentation as Code is a practice that involves treating documentation with the same principles as code. This means that documentation is version-controlled, tested, and built automatically. It is a concept that many software development teams have embraced due to its numerous benefits. This means writing documentation in formats that can be read and processed like code. This can include formats like Markdown or YAML and PlantUML or Mermaid (for diagrams), which can be stored in version control systems, reviewed in code review processes, and transformed into other formats like HTML or PDFs (and PNGs or SVGs for diagrams) using automated build systems.

### The Importance of Diagrams as Code to Compliance

Diagrams as Code are crucial for modern software development practices. It ensures that documentation stays up-to-date with code changes, improves the quality of the documentation, and makes it accessible to all team members. It also allows for code reviews and automated testing to improve the quality of the documentation. In traditional software development, documentation often falls behind the code because it is not integrated into the development process.

Diagrams as Code are pivotal to the Documentation as Code philosophy, enhancing clarity, maintenance, and collaboration. They enable teams to version-control visual documentation alongside code, ensuring that diagrams evolve with the system they describe. This integration facilitates automated generation and updates of diagrams, keeping documentation accurate and reducing manual effort. By treating diagrams as code, organizations can streamline documentation processes, improve understanding of complex systems, and foster better stakeholder communication.

### How applicable are diagrams as code?

What types of diagrams as code can you create that _apply to compliance_? Pretty much everything you need to make:

<figure><img src="https://www.dropbox.com/scl/fi/d9t7d5ph6bfwqyel0q3wo/UML-2.5-Diagrams.png?rlkey=j69yh59ndyo2ijr0w7l2k0hwc&raw=1" alt=""><figcaption><p><em> UML 2.5 Diagrams </em></p></figcaption></figure>

While compliance policies (both internal and external) are typically very well-defined, documentation on how exactly to carry out those policies effectively is not always well-defined or available. Creating detailed flow charts or workflows can benefit a corporate compliance department. Compliance workflows such as flow charts, ERDs, Sequence Diagrams, Dataflow Diagrams, etc., display the granular steps that need to be taken to ensure that the organization is in line with the internal controls set forth by management as well as the external obligations called for by governing bodies.

When it comes to compliance diagramming, choosing the right diagram type is crucial. Different compliance requirements may call for different types of diagrams to effectively communicate the necessary information. This section will explore various diagram types commonly used in compliance and discuss their suitability for different regulatory requirements.

## Process Flow Diagrams

Process flow diagrams are widely used in compliance to illustrate the sequence of steps involved in a particular process. These diagrams provide a visual representation of how activities are performed, the order in which they occur, and the inputs and outputs of each step. Process flow diagrams are particularly useful for documenting compliance processes, such as risk assessments, incident management, and change management.

When choosing process flow diagrams for compliance, it is important to consider the level of detail required. Some compliance regulations may require a high level of granularity, while others may only need a high-level overview. PlantUML provides a range of symbols and shapes that can be used to represent different process elements, making it a versatile tool for creating process flow diagrams for compliance purposes.

<figure><img src="https://www.dropbox.com/scl/fi/0fifzmtrbzqxhv2vbszi5/Process-Flow-diagram.png?rlkey=im2fss2kx4si78ghlqgvo112l&raw=1" alt=""><figcaption><p><em> Process Flow diagram </em></p></figcaption></figure>

## Dataflow Diagrams

Straight out of the FFIEC Operations Handbook,

> Management should develop data flow diagrams to supplement its understanding of information flow within and between network segments and across the institution’s perimeter to external parties.

That term, data flow (also spelled dataflow in the same documents), in combination with “maps,” “charts,” and “analysis,” appears 15 times in 5 different Handbooks: Development and Acquisition, Information Security, Operations, Retail Payment Systems, and Wholesale Payment Systems.

Here’s a sample that was used in an actual PCI audit:

<figure><img src="https://www.dropbox.com/scl/fi/gg8evvxwocu3dtdczn1sp/Compliance-Related-DFD.png?rlkey=5gm0s4yqwda37mcjxs2jgscxw&raw=1" alt=""><figcaption><p><em> Compliance-Related DFD </em></p></figcaption></figure>

The diagrams above were created by entering text into the UML editor, automatically creating the graphical version.

## Entity Relationship Diagrams

Entity Relationship Diagrams (ERDs) are used to illustrate the relationships between different entities in a system or process. These diagrams show how entities are related to each other through various types of relationships, such as one-to-one, one-to-many, or many-to-many. ERDs are commonly used in compliance to document data structures, identify key entities, and understand their relationships.

When choosing ERDs for compliance, it is important to consider the complexity and scope of the system or process being depicted. Compliance regulations often require organizations to demonstrate how they manage and protect data assets. ERDs can help visualize the structure of data and identify potential compliance risks or dependencies. PlantUML provides a range of symbols and connectors that can be used to represent entities and relationships, making it a valuable tool for creating ERDs for compliance purposes.

<figure><img src="https://www.dropbox.com/scl/fi/sgu24wdq2bmivnxvzvii9/Entity-Relationship-Diagram.png?rlkey=ratjsfng05bo5kerje7yv6sz9&raw=1" alt=""><figcaption><p><em>Entity Relationship Diagram</em></p></figcaption></figure> 

## Technical Structures

Technical structures, such as network diagrams (both simple and complex), can be created within UML. An example of a simple network diagram is here:

<figure><img src="https://www.dropbox.com/scl/fi/n6sshs389wmef7gejkefh/Simple-Network-Diagram.png?rlkey=1h4iw97pv39gnplhdao0mx5nf&raw=1" alt=""><figcaption><p><em>Simple Network Diagram</em></p></figcaption></figure>

With a more complex diagram here:

<figure><img src="https://www.dropbox.com/scl/fi/n0bls7qnrj1zdlcbylz88/Complex-Network-Diagram.png?rlkey=np41558c9zq4i8jvwe6muh5gm&raw=1" alt=""><figcaption><p><em> Complex Network Diagram </em></p></figcaption></figure>

And a deployment diagram here:

<figure><img src="https://www.dropbox.com/scl/fi/wmsek7bi4ngjes31wkm8q/Kubernetes-deployment.png?rlkey=grth8ejnk8862bf1e6ywsjha1&raw=1" alt=""><figcaption><p><em> Kubernetes deployment </em></p></figcaption></figure>

## Policy Creation

Creating policies doesn’t have to be like watching paint dry. You can whip up a policy creation process faster with diagrams as code than making instant noodles. It’s like having a GPS for navigating the bureaucratic maze of policy development. No more wandering in circles; just straight to the point, with some flair. Developing _rough drafts for flows_ can be done in under a minute using Generative AI that creates PlantUML diagrams. For instance, we wrote a prompt to create a PlantUML diagram using the first sentence in this paragraph, and it generated the following diagram in 30 seconds:

<figure><img src="https://www.dropbox.com/scl/fi/b559dcq7qazublfl70c2o/Policy-creation-diagram.png?rlkey=xbo93s5jw7iuzt5gj7oy79vq9&raw=1" alt=""><figcaption><p><em> Policy creation diagram </em></p></figcaption></figure>

This diagram can then be sent, along with the supporting text, to any stakeholders for editing. The text that is used to create the diagram is simple and easily understood:

```
@startuml
title Policy Creation Process
start
	: Identify Need for New Policy;
	: Research and Draft Policy;
	: Review and Approval by the Legal Team;
	: Senior Management Review;
	While (Approved by Management?) is (No)
		: Revise and Resubmit Policy;
	end while (Yes)
	: Communicate Policy to Employees;
	:Implement Policy;
	:Monitor and Review Policy;
stop
@enduml
```

## Policy Enforcement

Think of policy enforcement like a game of Whack-a-Mole but with less randomness and more strategy. Diagrams here are your mallet—swift, precise, and effective. By visualizing the enforcement process, you’re not just chasing issues reactively; you’re orchestrating a symphony of compliance, ensuring every note is played to perfection. Creating workflows, or flow charts, for the policy enforcement process can provide several benefits to the organization: decrease issue resolution times and case backlog, decrease compliance expenses, and increase trust from employees and shareholders. Step-by-step analysis and governance of the policy enforcement process will benefit employee relations, improve issue resolution operations, and boost overall compliance efficiency. An example of a policy enforcement workflow is the following Credit Card fraud resolution workflow:

<figure><img src="https://www.dropbox.com/scl/fi/9artrwu6lm1j2enffd7gf/Credit-Card-Policy-Enforcement.png?rlkey=ke0rz4r696uqb2bd10lil1qwx&raw=1" alt=""><figcaption><p><em> Credit Card Policy Enforcement </em></p></figcaption></figure> 

Here’s how this looks as text:

```
@startuml
autonumber
actor Caller as caller
boundary “Org System” as Org
actor Specialist as a specialist
Control system as system
actor “Escalation Team” as a team
group Inbound Call Processing
	caller -> system: begins fraud process
	system -> specialist: forward call
	specialist -> specialist: screens calls
	system -> specialist: populate the screen with client profile
	specialist <-> caller: determines the call is about
	specialist -> caller: reads disclosure
	caller -> specialist: responds at checkpoints
end

group Issue Resolution & Case Creation

	group Issue Process Determination
		Specialist -> specialist: Can I process this?
		
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
		Specialist -> caller: Review transactions
		
		group Transactions Verified
			specialist -> specialist: Review notes, determine cancellation
			the group Keep card open
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

## Risk Management

A risk management framework with process flows and checklists can help confirm that risks are identified, ranked, analyzed, responded to, and monitored. A well-defined risk management function can measure and track the risks that have been identified throughout the process. _Understanding the process_ is critical. There are several methods for risk assessment during various phases of software development and at different levels of abstraction. However, very few techniques are available for assessing risk at the requirements level, and those available are highly subjective and are not based on any formal design models. Such techniques are human-intensive and highly error-prone. Using the software’s Unified Modeling Language (UML) specifications at the early development stages allows each requirement to be mapped to a specific operational scenario in UML.

Several papers are dedicated to using UML for risk assessment and management[^ This is a really good one; K. Appukkutty, H.H. Ammar, K.G. Popstajanova, “Software Requirement Risk Assessment Using UML.”]. For example, the following diagram is a standardized threat model that can _begin_ a discussion between your dev/architect and compliance teams[^ The full UML text for this is found at Srinivasan, “Threatmodel-as-Code Using PlantUML.”].

<figure><img src="https://www.dropbox.com/scl/fi/8aty80iqutenncj2531h6/PlantUML-Threat-model.png?rlkey=m2alcb345erzv5qtcpnff0niz&raw=1" alt=""><figcaption><p><em> PlantUML Threat model </em></p></figcaption></figure>

## Internal Audit

There are two ways to look at using PlantUML for internal audit. The first is having an internal audit adopt it to document their processes. The second is having them _accept_ PlantUML diagrams for internal auditing purposes.

Since internal auditors’ primary responsibility is to ensure corporate policies and processes are being adhered to, they should also have flow charts for their auditing processes to ensure they assess and report the company’s operations correctly.

The concept of “code as documentation” is widely accepted in many fields, including auditing. Diagrams as code, such as those created with PlantUML, can serve as a form of easy documentation to maintain and update. This can be particularly useful in auditing contexts where understanding the system or process being audited is crucial. However, the acceptance of diagrams as code by auditors likely depends on the specific auditing standards and practices in place and the complexity of the system or process being audited.

## Regulatory Reporting

Documenting the regulatory reporting process is essential for the financial and reputational well-being of the company. Any missteps (unintentional or otherwise) in the regulatory reporting process can lead to penalties, fines, mistrust, or excessive scrutiny from regulatory bodies in the future. Depicting regulatory reporting processes through flow charts can guarantee that all necessary steps to report to regulatory bodies have been sufficiently completed.