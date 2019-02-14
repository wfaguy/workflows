# WFA maintenance

**Version 1.0.3**

If you are working with WFA quite a lot, there are some maintenance tasks that might be handy.  And they are either not possible in the GUI, or they take a lot of manual work.

* Clean ALL execution logs
* Clean ALL reservations
* Enable Full RBAC

## Cleaning all execution logs
These include both datasource execution logs & workflow execution logs.  
Why clean them ?  Maybe you want to give a demo and you want a clean start.  Maybe you prepared an environment for a customer and you want to clean you previous tests ?
Anyhow, in the gui you can't really clean them out.

You have the options
* All
* Before Timestamp
* By JobExecutionId
* By Workflow name

## Clean reservations
Same reason, maybe you did some tests, it's full of reservations, and you just want them cleaned out.  Instead of deleting them manually, why not just remove them all in one go.
Sometimes wfa is stuborn and you need to clean them 1 by 1.

You have the options
* All
* Before Timestamp
* By WorkflowUUID
* By JobExecutionId

## Enable full RBAC
see also [as command](https://github.com/wfaguy/commands/tree/master/Enable%20Full%20Workflow%20RBAC)

When you deploy a new WFA server, by default it has all of these demo workflows.  In the admin menu, you can hide those, but they are only hidden in the GUI.  In the API they are still very much accessible !

Why hide workflows ?  Well, in a production environment I'd rather say who can run what.   First of all, the default workflows are visible.   But often new workflows are created and by default they are also available for everyone.
If you truly want to hide them, you should restrict all categories.  But still, some workflows don't have a category.

This maintenance workflow will create a new "No Category" category, move all non-assigned workflows to that category AND will then restrict all categories.
Now no-one but the admins can run workflows by default and all categories must be assigned to users or groups.