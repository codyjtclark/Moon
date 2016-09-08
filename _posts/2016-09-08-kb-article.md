---
layout: post
title:  "Knowledge Base Article"
date:   2016-09-08
excerpt: "This is a KB Article I wrote for Informatica to help users prevent failed workflows from continualy running"
project: true
tag:
- Knowledge Base
- Informatica
- PowerCenter
comments: true
---
# Running a failed workflow causes the PowerCenter Integration Service to run it again immediately, resulting in key violations and data errors

## Problem Description
When a scheduled workflow fails, and is then run manually, the workflow succeeds; however, the complete time is later than the scheduled run time.
As soon as the workflow finishes, PowerCenter Integration Service runs it again.

## Cause
When a workflow fails, PowerCenter Integration Service removes the workflow from the schedule. However, it retains the scheduled information associated with the workflow.

You can re-establish the schedule by rescheduling the workflow or by manually running it. If you manually run the workflow, the PowerCenter Integration Service restores the workflow schedule. It detects that a scheduled time was missed, and it immediately runs the workflow to accommodate the missed schedule.

## Solution
​Before you manually start a failed workflow, Informatica recommends that you unschedule it first. When you unschedule the workflow first and reschedule it, after the manual run completes, PowerCenter Integration Service does not acknowledge any missed schedule.

Note: If you do not unschedule the workflow, and the PowerCenter Integration Service detects that the scheduled run time was missed, it immediately runs the workflow again.
{: .notice}

[See it live](https://kb.informatica.com/solution/23/Pages/54/335903.aspx?docid=335903&type=external&fromsource=eservice&index=1&myk=){: .btn}
