---
layout: post
title: CI/CD
---

# What is CI/CD?
CI/CD is a method to frequently deliver apps to customers by introducing  **automation** into the stages of app development. The main concepts attributed to CI/CD are continuous integration, continuous delivery, and continuous deployment. CI/CD is a solution to the problems integrating new code can cause for development and operations teams **AKA "integration hell"**

Specifically, CI/CD introduces ongoing automation and continuous monitoring throughout the lifecycle of apps, from integration and testing phases to delivery and deployment. Taken together, these connected practices are often referred to as a **"CI/CD pipeline"** and are supported by  development and operations teams working together  in an agile way.

## What's the difference between CI and CD (and the other CD)?
The acronym CI/CD has a few different meanings. The "CI" in CI/CD always refers to continuous integration, which is an automation process for developers. Successful CI means new code changes to an app are regularly built, tested, and merged to a shared repository. It’s a solution to the problem of having too many branches of an app in development at once that might conflict with each other.

The "CD" in CI/CD refers to continuous delivery and/or continuous deployment, which are related concepts that sometimes get used interchangeably. Both are about automating further stages of the pipeline, but they’re sometimes used separately to illustrate just how much automation is happening.

Continuous  _delivery_  usually means a developer’s changes to an application are automatically bug tested and uploaded to a repository (like  [GitHub](https://redhatofficial.github.io/#!/main)  or a container registry), where they can then be deployed to a live production environment by the operations team. It’s an answer to the problem of poor visibility and communication between dev and business teams. To that end, the purpose of continuous delivery is to ensure that it takes minimal effort to deploy new code.

Continuous  _deployment_  (the other possible "CD") can refer to automatically releasing a developer’s changes from the repository to production, where it is usable by customers. It addresses the problem of overloading operations teams with manual processes that slow down app delivery. It builds on the benefits of continuous delivery by automating the next stage in the pipeline.

It’s possible for CI/CD to specify just the connected practices of continuous integration and continuous delivery, or it can also mean all three connected practices of continuous integration, continuous delivery, and continuous deployment. To make it more complicated, sometimes "continuous delivery" is used in a way that encompasses the processes of continuous deployment as well.

In the end, it’s probably not worth your time to get bogged down in these semantics—just remember that CI/CD is really a process, often visualized as a pipeline, that involves adding a high degree of ongoing automation and continuous monitoring to app development.

Case-by-case, what the terms refer to depends on how much automation has been built into the CI/CD pipeline. Many enterprises start by adding CI, and then work their way towards automating delivery and deployment down the road, for instance as part of  cloud-native apps

Our experts can help your organization develop the practices, tools, and culture needed to more efficiently modernize existing applications and to build new ones.

##  What Is Continuous Integration and How to Benefit From It?

Your product ideas may be the greatest of all time, but without delivering well and delivering often, it may be extremely hard to keep up with the competition. In this article, we’ll show you how continuous integration and delivery can help you do just that.

What you’ll learn about in this article:

-   Benefits of CI/CD
-   How to maximize the value of CI/CD
-   Challenges
-   How to get started
###  Continuous integration, continuous delivery, and continuous deployment:
###  Continuous integration

Continuous integration (CI) is the software development practice of regularly integrating code changes into a shared code repository. Typically, this would happen at least once or then several times a day (depending on the number of code commits) and this practice encourages committing small changes more often over committing large changes infrequently. Each commit triggers a build during which tests are run that help to identify if anything was broken by the changes.

### Continuous delivery (CD) and continuous deployment

Continuous delivery is all about the ability to continuously deliver integrated code, be it bug fixes or new features, to production. It means that your “green builds” are ready to go in one click, should you wish to release them.

**Continuous deployment** goes one step further as it allows you to automatically deploy live every main branch change that passes the CI. However, you might have business reasons for not doing so automatically or you might need to do testing that can’t be automated.

### How to get started with continuous integration and delivery?
It’s really easy to get you up and running with the right continuous integration service. Here’s a really short list of basics you need to get started with CI.

-   Implement **version control** of your choice (Git, Bitbucket, SVN, etc).
-   **Write tests** for the critical components in your code base (and treat your tests as production code).
-   Get a suitable **continuous integration and delivery service** that will enable you to run those precious tests on every push to the repository and also deploy your builds where you need them.

### Benefits of continuous integration and delivery (CI/CD)
Let’s dig into what implementing continuous integration to your everyday software development process can bring to the table. Realizing these benefits means reducing risks for each build and clearing the way to get your valuable features out to customers faster.


**Fast feedback loop**. In software development, what you don’t know really can hurt you. If there’s anything that really slows you down when developing software, it’s the lack of feedback on the quality and impact of the changes you made. You might think you move fast if you quickly commit code and move on to another task without running any tests or sanity checks. The reality will hit you later when you’re trying to figure out which change and from when (and by whom…) broke something. Continuous integration tools — when properly used — will remove much of this headache by providing you with quick answers to the question “did I break something?” for each commit.

**Increase transparency and visibility**. When your CI/CD pipeline is set up, your entire team will know what’s going on with the builds as well as get the latest results of tests, which means they can raise issues and plan their work in context. You can see which changes tend to break builds more often.

**Avoid “integration hell”**. If you think of software as a set of Lego pieces, each of which is crafted by an individual developer separately, it becomes clear that making different pieces go “click!” without any effort and friction is what helps the team make progress every day. If a specific piece is fine on its own in terms of implemented code, you will still need to make sure it plays nice with everything else. Continuous integration supports connecting the pieces of your software every day.

**Detect and fix issues early**. The thing with bugs in software is that they hide other bugs that hide other bugs that… yes, you guessed it, hide more bugs. The more bugs pile up, the harder it is to test and find them, resulting in nasty last minute surprises (especially on a Friday night). If various kinds of useful automated tests are run in your continuous integration pipeline, you’ll be able to know what to fix as soon as a test fails. Not all of the testing can be automated and it takes time to automate what can be automated, but doing so helps you develop software in a sustainable way and keep the technical debt at a minimum.

**Improve quality and testability**. The easier it is to test something, the easier it is to determine its quality. Testability has multiple dimensions. On the inside, testability can be characterized by how controllable, observable, unbuggy, and decomposable your product is. Simply put, if your code is written in a way that doesn’t accommodate writing tests for it, you will have a hard time making it unbuggy. On the outside, testability is affected by how easily new builds are available, what kind of tools you have, and how much control you have over your test environments. Continuous integration and delivery drive both since you will need to write tests and run them, and also deliver builds frequently and reliably.



### Unit tests

Think strategically of the quality of your product to identify what kind of testing is the most valuable. Write unit tests to check your implementation of functions and methods.

### Integration tests

Write integration tests to ensure that different components work together. Set up acceptance tests to also validate important business requirements.

### UI Tests

Write UI tests to cover important user scenarios. Conduct exploratory testing to discover issues your automation wouldn’t find.

CI/CD tools can also support you by offering code coverage analysis to find untested code, overview of test results over time to see trends, etc. These are powerful functions that increase transparency and visibility which, in turn, help to make better decisions during the development process.



### How to choose the CI/CD tool for your needs

There are several continuous integration and delivery services that you can choose from depending on your needs. A few things to keep in mind when starting to research your choices:

-   **Open source vs proprietary**: depending on your context, open source tools may be off the table due to client requirements. If open source tools fit your budget and context better, there are options available, such as Jenkins. Before jumping to conclusions, get acquainted with the downside of open source CI servers.
-   **Self-hosted or in the cloud**: if you need to host the CI/CD service yourself and have the energy and time to set up, configure, and maintain it, you might go with something like Jenkins or CruiseControl. However, if you’d like to cross build infrastructure maintenance off your to-do list for good, you should look at a software-as-a-service type of solutions hosted in the cloud.
-   **Ease of setup**: making the adoption of CI/CD frictionless is perhaps key to getting everyone on board. A huge learning curve and effort for setting up a CI/CD pipeline may be hard to justify when you’re already pinched for time.
-   **Build status**: since adopting CI/CD is about transparency and visibility, it’s also important to make it visible and transparent your way. It might look like a nice-to-have thingy, but getting notifications in your Slack channel, via email or in other channels may improve the flow of information considerably.
