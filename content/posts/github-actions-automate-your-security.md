---
title: "GitHub Actions: Anatomy of a Workflow"
date: 2022-11-15T07:31:56+11:00
tags:
  - DevOps
  - GitHub
---

GitHub's automation feature GitHub Actions is a powerful devops automation tool built into GitHub. It can be used to automate many tasks in the platform using events to begin some sequence of actions. This can be used to build and deploy your application on a pull into main, deploy a docker image to your infrastructure.

Though before we get to using GitHub Actions, it'd be a good idea to learn a bit more about it's anatomy.

# Anatomy of GitHub Actions

## Workflow

The workflow is the encompassing structure of an Action. It contains all of the elements of one, including events and the jobs that they trigger. A workflow is defined in a `.yaml` file in the `.github/workflows` directory of a repsoitory. You can have more than one in a repository enabling a fair amount of flexibility in how you can use them.

## Events

A neat part of GitHub Actions is the amount of triggers, or Events that exist to start your Actions. For example you could run a workflow that adds important information whenever someone creates an issue, or tests a pull request whenever one is opened. This gives you quite a bit of versatility in your Actions, meaning you can use them beyond just devops operations.

## Jobs

Jobs are the part of an action that does stuff. They are composed of a series of steps that are run either in parallel, or in order, depending on if a sxtep relies on one that proceeds it. Each step is either a script or an Action, so you are able to keep them simple, or make them as complex as you desire. A key thing to note is that all steps within a job run on the same *runner*, meaning that you can share data between steps allowing for more interesting and complex jobs.

## Runners

Runners are servers that run a single job. GitHub provides a variety of different operating systems for runners, all of which execute in fresh virtual machines at runtime. If you have particular requirements for a runner you are also able to host your own.

## Actions

Actions are custom applications for the GitHub Actions feature. Much like a function they allow you to reuse a complex but repeatable action in your workflows. They are very powerful and can be used to do a number of different things. Actions can be custom built or can be selected from the GitHub Marketplace.

