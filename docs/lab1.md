---
title: Laboratory Exercise 1
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Models in Version Control

_The initial model in this repository comes from the [ESPD-EDM](https://github.com/OP-TED/ESPD-EDM) repository, licensed under the [EUPL-1.2 license](https://github.com/OP-TED/ESPD-EDM?tab=EUPL-1.2-1-ov-file#readme). For more information, see the [Technical Documentation](https://docs.ted.europa.eu/ESPD-EDM/latest/technical/index.html). Part of this file has been adapted from the [EU TED Portal](https://docs.ted.europa.eu/ESPD-EDM/latest/index.html)._

To download the initial model, click [here](assets/espd.qeax).

This laboratory exercise assumes pairs of people working together. Some steps refer to **Person A** or **Person B**. Ensure you agree on which one *you* are!


## Setup

**Person A**: Create a private repository on GitHub. Tick **Add a README file** so that the repository is initialized properly. Invite **Person B** as a collaborator. Add the linked model file (`espd.qeax`) to the repository, either via the web interface, or SmartGit.

**Both people**: clone the repository in SmartGit. Ensure you both can open the model file using Enterprise Architect.

## Introduction

The *European Single Procurement Document* (ESPD) is a mandatory electronic form, in two parts, used by buyers to assess the suitability of suppliers tendering in a public procurement procedure. The [model](espd.qeax) provided here showcases the ESPD Exchange Data Model (ESPD-EDM) to help member states and commercial entities create an ESPD service. 

Your tasks during this exercise will cover the following:

1. Create some (mock) documentation about the data model
1. Modify part of the data model and merge the modifications via the [GitHub Flow](https://docs.github.com/en/get-started/using-github/github-flow)  
1. Accept an incoming pull request and solve merge conflicts within the model file
1. (_Optional_) Create an activity diagram that showcases a possible flow of information using the ESPD data model.

## Creating Documentation

Throughout this subject, we will primarily grade **documentation**, never the model file itself. Good documentation is self-contained, includes good quality pictures of relevant parts of the model, alongside engineering decisions and explanations of the solution. 

**DO:** Create a new file in the repository, called `Documentation.md`. Using [GitHub Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax), include diagram renders in the document using the [image](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#images) syntax. You may exclude diagrams that have no meaning (such as the LostAndFound diagram).

Also try and include some descriptions on what each diagram represents. The resources linked at the top of this file can help you determine their purpose. Do not overdo this step, a few sentences are more than enough.

## Model Change and 2-Way Merge

Open `espd.qeax` in Enterprise Architect if you haven't done so already.

Next, locate `cac::QualificationApplicationRequest` either in the model hierarchy or on one of the diagrams. We want to change this element so that `issuetime` is not optional, and `previousversionid` may contain any number of entries. We also want to add a child class,`cac::SpecialQualificationApplicationRequest`, inheriting from this base, to allow specialization later on.

**DO**: 

1. **Person A only**: Change the multiplicities of these attributes to the desired values outlined above, create the child class on the diagram where `QualificationApplicationRequest` was found, and open a PR from a feature branch towards `main`. Do not yet merge. 
1. **Person B only**: Change the multiplicity of `issuetime` to `2..2`, and open a PR from a feature branch towards `main`. Do not yet merge.
1. **Both people**: Inspect each other's pull requests, both on GitHub and in LemonTree (double click the file in SmartGit!)
1. **Person A only**: Merge **your partner's** pull request. Do not update your own.

> This type of merge is called a _2-way merge_, because we merge two branches that have not diverged. Therefore, there cannot be any merge conflicts, every change is present on the same (feature branch). This means the model file (which is not a text file) is just overwritten by the version from the feature branch. Had the two branches diverged, this would be a _3-way merge_, and `git` alone could not solve the merge conflicts within this non-text file.

## Causing a Conflict and 3-Way Merge

In this step, we will resolve the merge conflict in the other pull request, using SmartGit/LemonTree. When ready, we will merge the PR.  

**DO**: 

1. Open SmartGit, checkout `main` (double-click) then click `Pull` to pull the changes.
1. Checkout the source branch of the PR, then select `main` and click merge in the right-click (context) menu. A prompt should appear asking how the merge should be performed. Choose `Create Merge-Commit`. This will open the merge window, where conflicts have to be dealt with.
1. Double-click the conflicting `espd.qeax` to open in LemonTree.
1. After LemonTree opens, there are 3 columns in the right partition: "ours", "theirs", and "target". We can see the current feature branch's modifications in the "ours" column, the second feature branch's modifications in the "theirs" column, and the desired outcome in the "target" column. Pick the model elements to keep -- remember the goal of the previous step.
1. Push your local changes to GitHub, and merge the PR.

## (_Optional_) Creating an Activity Diagram

Next, you'll create an activity diagram showcasing how information may flow using the ESPD data model. You can find information in the resources linked above, but you may also assume a simple workflow. The realized process itself will not be graded.

**DO**:

1. Open an issue in the repository, stating the expected behavior (textually). Assign yourself to the issue.
1. [Link](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue) the pull request to the issue so that when the PR is merged, the issue is automatically closed.
1. Merge the PR.

> In Enterprise Architect, creating an Activity Diagram can be a bit complicated. Feel free to search online for guides and documentation, such as [this](https://sparxsystems.com/resources/tutorials/uml2/activity-diagram.html) one, or our own modeling guide [here](../behavior-modeling-guide).
