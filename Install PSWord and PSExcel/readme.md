# Install PSWord & PSExcel
When you want to work with Excel and Word documents from within WFA, you either choose to install Excel and Word, or, way better, you choose for the PowerShell Modules
* PSExcel
* PSWord

This workflow will install these for you on the WFA server on the right location.  The actual source files are safely hidden in the help content of the workflow.

You can install and remove.  The remove acts a bit funny now and then, if files are still locked.  Just run it twice if needed, but then again, you will just install and leave it at that :)

# Hidden files
You might wonder where the files are.  Good question.  You can add help-files to a workflow.  They are hidden there.  During the install workflow, I just copy them.