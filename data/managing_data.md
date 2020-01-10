# Managing data

Menu: **[data]**

The data page displays all of your uploaded data such as (VCFs, Bed files, Pedigree Files etc)

Data is displayed in grids, with each data type in a separate tab.

You can enter parts of the name into an autocomplete search box to quickly find your files:

![](images/sample_autocomplete.png)

Click the link on the grid to view the file details page.

## Sharing data

Users belong to groups (see [user settings](../settings/user_settings.md)) that can share data. Ticking the **Show Group Data** checkbox will show this on a grid.

By default, you automatically share data (read-only) with your group.

To change data permissions, click the **[Data/Sharing]** tab:

![](images/data_sharing_permissions.png)

**logged_in_users** is a special group - and means everyone who has a VariantGrid account.

### HGVS

We use [PyHGVS](https://github.com/counsyl/hgvs) library for parsing HGVS names, which supports 'c.', 'n.' and '.p'.
