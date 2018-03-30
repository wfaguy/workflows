# Runspace Workflow
Invoking a workflow in a workflow.  It's been done before.  Of course we can have subworkflows (1 level deep).
But I'm talking about invoking a loop-back (localhost) rest-call.

When done in the traditional way, usually for something simple like the default "acquire datasource" workflow, it's something like : invoke-rest - wait - check result.
Maybe even with a repeat-row, like Tim Kleingeld did with his lun migrations a few years back.

If we mean serious business, we need something more solid, more thought-through.

Read the full article [here](http://www.wfaguy.com/2018/03/wfa-sub-workflow-runner-template.html)

## Runspaces
The concept and this template is using runspaces, so definitely check out [my post about runspaces](http://www.wfaguy.com/2018/03/run-powershell-scripts-in-parallel.html).
We just wrap this concept in a WFA command.

## Purpose
The purpose of this runner-template is to process massive amounts of workflow-calls.  Imagine that you wrote a monster workflow to provision volumes (with snapmirror, snapvault, ... the full monty)

And now you need to run this 100 times.  Maybe it's so massive that you need to build in auto-resumes, timeout-handling, etc...

**Some real-life examples where I'm using this already**
* provisioning for massive migrations
* post enabling snapmirrors
* creating storageX policies
* creating DFS links

