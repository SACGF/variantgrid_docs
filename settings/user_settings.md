# User Details

At the top of the page you can set your avatar image, and change your name/email etc.

The avatar is only used on the labs page,  **[Classification] -> [Labs]**

## Groups

Groups are used to share data (analyses, classifications etc) between users. If you search for a user in the search bar, you can see groups you have in common with them (so can use to share things by assigning permissions on objects for that group)

Your groups are set by administrators.

There are two groups that every user is a member of:

 * Logged_in_users - visible to anyone with a login
 * Public - visible to everyone (if in the future we allow access w/o a password)

## Initial group permissions

This lists your groups, whether they are associated with a lab or not. Labs are used for classification share levels.

The check boxes can be used to set initial object permissions, for instance if you set "read" for "mylab" then every time you uploaded a VCF, or create an analysis, it would be visible to people in "mylab".

This is just the initial setting, you can always click the "sharing/permissions" tab on an object then modify it later.

## Node counts

These are how the node counts are set when an analysis is created. You can always adjust each analysis node counts via analysis settings.

## User Settings

There are multiple levels of settings:

 * Global (set by administrators per server)
 * Default Lab's Organisation
 * Default Lab
 * User

The later settings can be used to overwrite the earlier ones if they don't like the defaults.

 * **Email Regular Updates** - Opt into email list (Only used for Shariant)
 * **Columns** - Default value to sort analysis grids (can be changed per analysis)
 * **Default Sort by Column** - Initial sort by column for analysis variant grid
 * **Tag colors** - Set of colors assigned to tags (modify/create these in 'Tag settings')
 * **Variant Link in Analysis Opens New Tab** - Whether left click by default opens up variant details in new window. Default is open where node editor is. You can always open in new window via right click then new window
 * **Tooltips** - Show/hide help popups on mouse hover
 * **Node Debug Tab** - If true, an extra tab appears in analysis node editor, with details about node settings + SQL query.
 * **Import Messages** - Get internal notification (message icon top left) when imports done (eg VCF finished processing and annotating)
 * **IGV Port** - Port to connect to IGV on your machine, see [IGV Integration](igv_integration.md)
 * **Default Genome Build** - Used for search (jump to result if that is the only one for this build) and populating defaults everywhere
 * **TimeZone (for downloads)**  - Time/date used in classification download
 * **Default Lab** - Lab used for creating classifications (you can belong to more than 1 lab)