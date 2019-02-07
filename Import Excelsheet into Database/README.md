# workflow

This workflow imports a worksheet from an excelfile into a table of the database.
Perfect for bulkactions, such as create bulk volumes, ...
You could also use this workflow to restore data in a custom table (as export you can use the export workflow from the EDM pack)

# requirements

- the excel pstool must be installed (see psexcel and psword install workflow OR use EDM pack)
- the excelsheet must have a table with matching fieldnames, don't use fieldnames ending with \_id

# thoughts

This could be expanded with functionalities such as :

- map 1 worksheet to 1 table
- use excel file as databasename

This would then have the same functionality as the EDM datasource (but in workflow form)
