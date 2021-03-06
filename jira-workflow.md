# Why JIRA, why?

JIRA fills a multitude of roles and it is unfair to simply call it our
bug-tracker. An outline of what its actual use might shed some light on
why the quality of the content is important to our process.

# Roles of JIRA

- Planning development
- Tracking dependencies
- Visualising progress
- Capturing decisions and information
- Displaying relevant information
- Release management
- Exposing our process
- Managing expectations
- Roadmap
- Quality assurance
- Bug tracking
- Communication hub

# Hard and fast rules

1. _Information related to the issue belongs in the issue_

*Slack* is great for discussions but it *is* a walled garden that holds the
history of those discussions hostage unless you pay up for a commercial
license. The search is beyond useless so everything written there can be
considered gone from our collective history.

The same goes for when discussing an issue with a colleague AFK or over e-mail.
Copy-paste the relevant part of the discussion, at least the decision taken and
the arguments for doing so, into a comment in the JIRA issue. Put it in
`{quote}` tags, mention the people who were involved (they should have a JIRA
account) so there is some way to trace decisions taken on issues in the future.

DHIS2 will live a long time and JIRA is our source of truth of what happens
throughout the lifetime of the project on all levels of the software. It is our
commit history and should be treated as such.

**A summary of a discussion related to an issue in JIRA needs to be added as a
comment to the JIRA issue**. 

Not to mention that if a developer becomes out of commision for a while work on
her features do not grind to a halt if the information is in the JIRA ticket,
and since we work on a prioritised backlog, whatever she was working on is
important to complete.

2. _Transparency is a good thing for everyone_

JIRA is our tool for showing all interested parties from implementors, donors,
product managers, internal and external developers, what we are doing, when we
are doing it, and why we are doing it.

**We are an open-source project, so hiding our inner workings behind closed doors
is detrimental to the values of open-source software.**

3. _The status in JIRA should reflect the truth_

This should be obvious, but we do not assign issue to ourselves we aren't
actively working on. It's more important that JIRA reflects the truth than to
look busy. If an issue is blocked, link it to the blocking issue and flag it to
your team leader or product manager. There is no reason to assign issues to
yourself or set them to in progress unless they are actively worked on, it just
stops someone else from starting on those issues.

**It's better to set an issue to unassigned than to look busy.**

# Statuses and what they mean

* **Open**: a fresh issue which isn't evaluated if and when it is going
  to be implemented. As a developer ignore these unless asked to help
  out with them.

* **Todo**: these issues have been considered by the product manager and
  are deemed to be important enough to be implemented. These issues are
  considered as part of the backlog.

* **In progress**: a developer has assigned himself to the issue and has
  started work on it.

* **In review**: the implementing developer thinks this issue is complete and
  needs someone to review it.

* **Testing**: hand-over to the QA-team for verification.

* **Done**: issue has passed QA tests and is closed and ready for release.

* **Needs update**: issue fails some QA tests, which might be lack of test case,
  documentation, or something else.
  
* **Re-opened**: issues that were at one point considered closed and done, but no longer are.

# Workflow

In general the happy case flow is:

1. Open
2. Todo
3. **In progress**
4. **In review**
5. Testing
6. Done

The parts of the flow in bold are the states we are responsible for doing work in. We take "todo" issues and transition them to "in progess". Here we do work. We then transition them to "in review" where we also do work to verify that they are good enough (according to our **Definition of Done**). When we are confident we move it to "testing" and it is out of our hands (in theory).

There are some criteria for actions before transitioning an issue along the
pipeline.

### Open

* Product manager prioritises

### Todo

* Part of backlog
* Plan for milestone
* [Evaluate issue completeness](#is-an-issue-ready-to-be-worked-on)

### In progress

* Assign to self
* Work has started

### In review

* As *assignee*: 
* * Unassign issue when transitioning so anyone on the team can review
* As *reviewer*:
* * [Review checklist](#review-checklist)

### Testing

* Unassign issue when transitioning to "testing"
* Picked up by testers automatically, they assign it to themselves when testing
  starts

### Needs update

* Happens when QA fails

### Re-opened

* Happens when there is a regression in relation to the issue

# Review checklist

## Bugs

* Is the Pull Request good to merge?
* Did you test the branch locally?
* Is there a test case linked to the JIRA issue?

## Features

* Is the Pull Request good to merge?
* Did you test the branch locally?
* Is the user documentation updated?
* Is the implementer documentation updated?
* Is there a test case linked to the JIRA issue?

# Is an issue ready to be worked on?

After reading the description of an issue, ask yourself these questions:

* Do I understand *why* this needs to be done?
* Do I understand *what* needs to be done?
* Do I have an idea of *how* this can be done?

Our job is to determine if the description is well enough defined that
we understand the *functional requirements* of how this is going to be
used.

If we do not understand the *why*, *what*, and *how*, then we need to
ask for more information so that we know that **we are building the
right thing**.

For *features* that might mean asking for use cases, diagrams, flow
charts, better description of the problem we are attempting to solve,
etc.

For *bugs* it might mean asking for a *test case* to reproduce the issue
(which saves you the trouble of writing one later), or a step-by-step
list of how to reproduce the problem, what the *expected behaviour* is
and what the *actual behaviour* was.

All this needs to be captured in the JIRA ticket as well, so if it's not
there and you cannot help out writing it, do not hesitate to re-assign
the issue to the **reporter** and asking for clarification.
