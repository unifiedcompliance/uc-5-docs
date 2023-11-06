# Workspace Settings

Note:  This option/page is only available to users with the Owner or Administrator role.

Use the Workspace Settings page to manage the following settings:

**General**

The General tab allows you to:

* Update Workspace Name - enter a new name and select _Update_
* Delete a Workspace - only the Owner can delete a workspace.  Once completed, you will be logged out of the application. Your workspace and associated content will remain available for the life of your subscription, but when it expires, all content will be permanently removed. &#x20;

**Joining**

The Joining tab allows you to configure self-registrations for users wanting to join your workspace:

* Allow self-registrations with approval - users can request to join your workspace that then requires an approval from the Owner / Administrator
* Allow self-registrations and auto approve for certain domains - users can register and if their email domain matches one of those you have configured, then the user will automatically join your workspace.  Enter a comma-separated list of domains (ie. "unifiedcompliance.com").

Choose one of the options above and then select _Update_ to save the changes.

**Sharing**

The Sharing tab allows you to configure whether your workspace can contribute / publish PlantUML diagrams to the Community or not.  After specifying a handle and display name and saving them, the _Publish / Unpublish_ options will appear for your PlantUML diagrams.

* Unique Handle - specify a handle value for your workspace. This will appear in the Authority Source column of your diagrams in the PlantUML Community tab.  The value must be unique across the system (when you stop typing a notification will appear whether the value is unique or not).
* Display Name - specify a display name for your workspace. This will appear in the Authority Source column of your diagrams in the PlantUML Community tab.

Select _Update_ to save your changes.

* Delete Community Profile - this will remove all diagrams published to the Community (they will still appear in My Diagrams) and also remove the Publish / Unpublish menu option from your diagrams.

**API**

The API tab allows you to generate API Keys for your workspace.  A valid API Key must be sent in an authentication header when calling any of the Unified Compliance REST-based APIs.

Enter a name for the API Key and then select _Create_.  The new API Key will appear. [CAUTION](https://gitlab.com/UnifiedCompliance/software/unified-compliance-frontend/-/merge\_requests)! Be sure to use the _Copy API Key_ button to immediately copy the API key as it will no longer be visible to you once you leave the page.  Optionally use the _Revoke_ button to remove an API Key.

The list of API Keys created in your workspace will then appear where you can manage them accordingly (modify the name or revoke).