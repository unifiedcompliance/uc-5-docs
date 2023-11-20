# Wireframes

The wireframes for the PlantUML MVP are fairly simplistic as well.

The assumption is that this MVP is **built upon the Core Account MVP** that already has the flows and structures for establishing an account and connecting the account to the Compliance as Code API gateway.

* All wireframes in Balsamiq format can be found at https://balsamiq.cloud/srj76i4/puiw8kt.
* All wireframes in Figma format can be found at

#### Landing Page

![Landing page](https://www.complianceascode.net/wp-content/uploads/2021/10/UML-Landing-Page-Default.png)

1. Account information can be accessed by clicking the cog in the bottom left of the main navigation pane.
2. The icon for the main navigation will be the design icon.
3. Basic information for the landing page will be presented, along with a link to the documentation for the MVP.

![Landing navigation open](https://www.complianceascode.net/wp-content/uploads/2021/10/UML-Landing-Page-Navigation-Open.png)

1. When opened, the main navigation will show two sub pages - the **Library** and the **Workspace**.

#### Library

The PlantUML Library contains a listing of all of the available diagrams that the organization has either created itself, or downloaded through the API. This window allows the user several options for working with these files _except_ for creating a new one (which is done in the Workspace).&#x20;



![Library](https://www.complianceascode.net/wp-content/uploads/2021/10/UML-Library.png)

1. The table of information will contain the following:

* **Published** status of the record indicated that it has been published to the federated database.
* **Diagram Type** which is derived from a known list of diagram types as described above.
* **Diagram Name** is the name of the diagram and corresponds to the _description_ element in the schema.
* **Creator** will either be the local name of the person who created the wireframe, or if the wireframe was created in the federated database, we will allow “federated user” to be placed there. It would be _better_ if the name were drawn from the _audit data_ of the federated system, but for version 1 of the MVP “federated user” will work.
* **Modifier** is to be treated the same as the _Creator_ above.
* **Modified Date** is either the last date of a local modification or the _‌date\_modified_ element from the schema.
* **Group** is drawn from the list of local groups that the diagram can be assigned to. Or, _All_ is to be used if no group is assigned. This is really just for filtering the various diagrams.
* **Select** is a radio button in this diagram and the way that the user selects the record for an action.

2\. **Search** is an open-text search field that _can be_ constrained by a drop-down filter.

3\. **Record management** buttons should include the following:

* **Open** to open the selected record.
* **Duplicate** would then bring up a dialog to name the duplicate record before duplicating it.
* **Rename** allows the user to rename _local_ diagrams, but _not_ diagrams that are published in the federated database.
* **Delete** should bring up a warning dialog before deleting the record.

4\. An **Import** button will bring up a window (shown below) to import records from the federated database.

#### Import published diagrams

Import published diagrams The _contents_ of the window to import published diagrams is very much like the library window, with two exceptions:

* **Published** is replaced by **Validated**, and
* **Group** has been removed.

![Import Window](https://www.complianceascode.net/wp-content/uploads/2021/10/Import-Published-Diagrams-1.png)

#### UML Workspace

The UML workspace allows the user to enter text in the text field and then display it in the GraphViz field above.

![UML Workspace](https://www.complianceascode.net/wp-content/uploads/2021/10/UML-Workspace.png)

1. This is a _resizable_ diagram window controlled by GraphViz that displays the contents of the text field.
2. This is a _scrollable_ window that maintains the same width of the graph above and allows the text to be entered.
3. The **Refresh** button redraws the graph of the text.
4. The graph management buttons (New, Save, Export, Delete) allow management of the record. To note, the **Export** button should give the user the choice of exporting the text of the graphic, or a PNG of the graphic.
5. The **Publish** button can only be active if the _User_ has registered as a **Person** or the _Organization_ has registered as a contributor. If this button is active, the API process for posting a new record or updating the record in the federated database should be activated.
