# Configuring administrator roles

Administrators are the users of an admin panel of a Strapi application. They administrator accounts as well as the roles they are attributed are managed through the Role-Based Access Control (RBAC) feature, which settings are in the *Administration panel* category of the Settings interface, accessible from *General > Settings* in the main navigation of the admin panel.

![Administrator roles interface](../assets/users-permissions/administrator_roles.png)

By default, 3 administrator roles are defined for any Strapi application:

- Author: to be able to create, manage and publish their own content.
- Editor: to be able to create content, and manage and publish any content.
- Super Admin: to be able to access all features and settings. This is the role attributed by default to the first administrator at the creation of the Strapi application.

::: warning ATTENTION
If you use your Strapi application with the Community Edition (see [Pricing and Plans](https://strapi.io/pricing)), your use of the RBAC feature will contain some limitations. Only the 3 default role are indeed available, as you cannot create more roles and cannot delete the default ones. It is however possible to edit them, to an extent:

- Configuring permissions in detail is only available for the Enterprise Edition: with the Community Edition, if you have access to a content type, it is automatically a full access with all permissions.
- You can only configure permissions for the content types, but not for the plugins and settings of the Strapi application.
- Custom conditions defined for a specific permission are also only available for the Enterprise Edition.

:::

## Creating a new role

On the top right side of the *Administration panel > Roles* interface, an **Add new role** button is displayed. It allows to create a new role for administrators of your Strapi application.

To create a new role, click on the **Add new role** button. 
Clicking on the **Add new role** button will redirect you to the roles edition interface, where you will be able to edit the role's details and configure its permissions (see [Editing a role](#editing-role-s-details)).

::: tip 💡 TIP
In the *Roles* interface, from the table, you can click on the duplicate icon to create a new role by duplicating an existing one.
:::

## Deleting a role

Administrator roles can be deleted from the *Administration panel > Roles* interface. However, they can only be deleted once they are no more attributed to any administrator of the Strapi application.

To delete a role:

1. Click on the delete icon on the right side of the role's record.
2. In the window that pops up, click on the **Yes, confirm** button to confirm the deletion.

::: tip 💡 TIP
You also have the possibility to delete multiple roles at the same time. To do so, select the roles by ticking the box on the left side of the roles' record. Then, click on the **Delete** button in the top right corner of the table.
:::

## Editing a role

![Administrator roles edition interface](../assets/users-permissions/administrator_roles-edition.png)

The role edition interface allows to edit the details of an administrator role as well as configure in detail the permissions to all sections of your Strapi application. It is accessible from *Administration panel > Roles* either after clicking on the edit icon on the right side of a role's record, or after clicking on the **Add new role** button (see [Creating a new role](#creating-a-new-role)).

::: warning ATTENTION
It isn't possible to edit the permissions of the Super Admin role. All configurations are in read-only mode.
:::

### Editing role's details

The details area of an administrator role editing interface allow to define the name of the role, and to give it a description that should help other administrators understand what the role gives access to.

::: tip 💡 TIP
In the top right corner, you can see a counter indicating how many administrators have been attributed the role.
:::

To edit a role's details, follow the instructions from the table below:

| Role details  | Instructions                                                                                                                     |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Name          | Write the new name of the role in the textbox.                                                                                   |
| Description   | Write the description of the role in the textbox.                                                                                |

### Configuring role's permissions

The permissions area of an administrator role editing interface allows to configure in detail what actions an administrator can do for any part of the Strapi application. It is displayed as a table, split into 4 categories: Collection Types, Single Types, Plugins and Settings.

#### Collection and Single Types

The Collection Types and Single Types categories respectively list all available collection and single types for the Strapi application. For each content type, the administrators can have the permission to perform the following actions: create, read, update, delete and publish.

To configure Collection or Single Types permissions for a role:

1. Go to the Collection Types or Single Types category of the permissions table.
2. Tick the box on the left of the name of the content type to give access to. By default, all actions can be performed for all fields of the content type.
3. (optional) Untick the action-related boxes to prevent actions of your choice.
4. (optional) Click the name of the content type to display its full list of fields. Untick the field and action-related boxes to prevent access and/or action for the fields of your choice.
5. Repeat steps 2 to 4 for each content type available to which the role should give access.
6. Click on the **Save** button on the top right corner.

#### Plugins and Settings

The Plugins and Settings categories both display a sub-category per available plugin or setting of the Strapi application. Each sub-category contains its own specific set of permissions.
To configure plugins or settings permissions for a role:

1. Go to the Plugins or Settings category of the permissions table.
2. Click on the name of the sub-category which permissions to configure, to display all available permissions.
3. Tick the boxes of the permissions the role should give access to. You can refer to the table below for more information and instructions.

:::: tabs

::: tab Plugins

By default, plugins permissions can be configured for the Content-Type Builder, the Upload (i.e. Media Library) plugin, the Content Manager, and Users Permissions (i.e. the Users & Permissions plugin allowing to manage end-users). Each plugin has its own specific set of permissions.

| Plugin name          | Permissions |
| -------------------- | ----------- |
| Content-Type-Builder | <ul><li>General</li><ul><li>"Read" - gives access to the Content-Types Builder plugin in read-only mode</li></ul></ul> |
| Upload <br> *(Media Library)* | <ul><li>General</li><ul><li>"Access the Media Library" - gives access to the Media Library plugin</li></ul></ul> <ul><li>Assets</li><ul><li>"Create (upload)" - allows to upload media files</li><li>"Update (crop, details, replace) + delete" - allows to edit uploaded media files</li><li>"Download" - allows to download uploaded media files</li><li>"Copy link" - allows to copy the link of an uploaded media file</li></ul></ul> |    
| Content-Manager | <ul><li>Single types</li><ul><li>"Configure view" - allows to configure the edit view of a single type</li></ul></ul><ul><li>Collection types</li><ul><li>"Configure view" - allows to configure the edit view of a collection type</li></ul></ul><ul><li>Components</li><ul><li>"Configure Layout" - allows to configure the layout of a component</li></ul></ul> |
| Users-Permissions | <ul><li>Roles</li><ul><li>"Create" - allows to create end-user roles</li><li>"Read" - allows to see created end-user roles</li><li>"Update" - allows to edit end-user roles</li><li>"Delete" - allows to delete end-user roles</li></ul></ul><ul><li>Providers</li><ul><li>"Read" - allows to see providers</li><li>"Edit" - allows to edit providers</li></ul></ul><ul><li>Email Templates</li><ul><li>"Read" - allows to access the email templates</li><li>"Edit" - allows to edit email templates</li></ul></ul><ul><li>Advanced settings</li><ul><li>"Read" - allows to access the advanced settings of the Users & Permissions plugin</li><li>"Edit" - allows to edit advanced settings</li></ul></ul> 👉 Path reminder to the Users & Permissions plugin: <br> *General > Settings > Users & Permissions plugin* | 

:::

::: tab Settings

Settings permissions can be configured for all settings accessible from *General > Settings* from the main navigation of the admin panel: Media Library and Webhooks (*Global settings* category) and Users & Roles (*Administration panel* category, to configure the settings of the RBAC feature). Settings permissions also allow to configure access to the Plugins and Marketplace sections of the admin panel. Each setting has its own specific set of permissions.

| Setting name            | Permissions |
| ----------------------- | ----------- |
| Media Library | <ul><li>General</li><ul><li>"Access the Media Library settings page" - gives access to Media Library settings</li></ul></ul> 👉 Path reminder to Media Library settings: <br> *General > Settings > Global Settings - Media Library* |
| Plugins and Marketplace | <ul><li>Marketplace</li><ul><li>"Access the Marketplace" - gives access to the Marketplace</li></ul></ul><ul><li>Plugins</li><ul><li>"Install (only for dev env)" - allows to install new plugins when in a development environment</li><li>"Uninstall (only for dev env)" - allows to uninstall plugins when in a development environment</li></ul></ul> |    
| Webhooks | <ul><li>General</li><ul><li>"Create" - allows to create webhooks</li><li>"Read" - allows to see created webhooks</li><li>"Update" - allows to edit webhooks</li><li>"Delete" - allows to delete webhooks</li></ul></ul> 👉 Path reminder to Webhook settings: <br> *General > Settings > Global Settings - Webhook* |
| Users and Roles | <ul><li>Users</li><ul><li>"Create (invite)" - allows to create administrator accounts</li><li>"Read" - allows to see existing administrator accounts</li><li>"Update" - allows to edit administrator accounts</li><li>"Delete" - allows to delete administrator accounts</li></ul></ul><ul><li>Roles</li><ul><li>"Create" - allows to create administrator roles</li><li>"Read" - allows to see created administrator roles</li><li>"Update" - allows to edit administrator roles</li><li>"Delete" - allows to delete administrator roles</li></ul></ul> 👉 Path reminder to the RBAC feature: <br> *General > Settings > Administration Panel* | 

:::

::::

4. Click on the **Save** button on the top right corner.

### Settings custom conditions for permissions

For each permission of each category, a **Settings** button is displayed. It allows to push the permission configuration further by defining conditions.
