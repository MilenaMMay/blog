# Optimizing your development and deployment workflows

**Integrate early and often!** 🤝

Why? Because humans are bad at keeping multiple realities in their minds.

Integrate your changes as soon as possible to remove the mental load of having different mental models how the code looks like when thinking about new features or bugs.


**Automate all the things!** 🤖

Why? Because computers are better at repetitive work than humans. And repetitive work sucks. 

Don't waste your energy making mistakes with repetitive work. Leave it to the computers and focus on creative work instead.


## Are you really doing CI/CD yet?

There's a common misunderstanding about tools and practices around CI/CD (Continuous Integration / Continuous Delivery).

The _practice of Continuous Integration_ means more than just using a _Continuous Integration Tool_ like Circle CI, Jenkins, GitHub Actions, Travis CI or else.

Don't be sad if you discover after reading this that you're not doing CI/CD yet. Each step towards CI/CD provides value in itself.

Take it as a challenge and see how close you can get. 🚀


## Test Automation ✅

If you pushing a commit to a repository and your CI tool executes tests and checks automatically, telling you when you broke something (for existing functionality that's called regression testing), you have a Test Automation in place.

**Why?**

😌 To have good confidence that your code is working as expected.

### Good practices about Test Automation

* have a good test coverage
* mind the test pyramid: 
    1. have **many fast tests** that check all **edge cases** with a **low level of integration** so that you can discover easily where something breaks
    2. and **few slow tests** that check the **happy paths** with a **high level of integration** so that you discover easily that your components don't work together as expected
* tests / checks to automate:
    1. Unit and Integration Tests verify your code works as expected
    2. Static Code Analysis (Linting, Type Checking, Code Quality Analysis) verifies the correctness and quality of your code
    3. Contract Tests (Consumer Driven Contract Tests, schema checks) verify your code can interact with other parts of the system
    4. System Tests (e.g. Smoke Tests) verify your code didn't break the system - careful: if you make this a quality gateway you might not be able to deploy if other parts of the system are broken

👉 How much do you test manually before you confidently release to production? Can you automate more of it?


## Release Automation 📦

If you're pushing to a specific branch (e.g. main) and - best after passing the quality gateway of your Test Automation - the branch gets deployed on Production, you have Release Automation in place.

**Why?**

🚀 To deliver features and bug fixes fast and without making manual errors in the deployment process.

### Good practices about Release Automation

* have a Test Automation as a quality gateway
* deploy to a non production environment first and only if successful to production
* deploy to a non production environment with the same tools and parameters to have a production like environment for (manual) testing
* keep the change-set small and especially do not pile up changes on non-production environments
* have a strategy how to fix production fast when breaking it (rollback, fix forward)

👉 How many steps do you need to perform to release to production? Can you make it just one?


## Continuous Integration 🔜 🤝

If you're merging (= integrating) every commit you push into your main branch, you're doing Continuous Integration. If you have Test and Release Automation in place and are pushing to (feature) branches, you're not really doing Continuous Integration, because you still need to merge (= integrate) your changes.

**Why?**

🤯 To avoid merge hells.

### Good practices about Continuous Integration

* have a Test Automation in place to ensure your commit doesn't break existing functionality
* if your commit makes the main branches Test Automation fail, roll it back
* craft your commits and their messages carefully because when working with several people on the same branch you shouldn't rewrite your commit history
* include the ticket number in your commit messages so that you can do a joint review of commits that belong together even if there are other commits pushed in between

👉 How often are you merging to your main branch? Can you increase it to several times per day?


## Continuous Delivery 🔜 📦

If you're pushing every commit to your main branch and it that gets deployed by your Release Automation, you're doing Continuous Delivery. Having a Release Automation in place and commits that lie on branches means you're not really doing Continuous Delivery because these commits are not in Production.

**Why?**

🧑‍💻 So that your software is used. Piling up features that are not used might led to wrong assumptions about your user's needs. This also helps to discover errors in your code that weren't caught by the Test Automation with your monitoring.

### Good practices about Continuous Delivery

* have a Test Automation as a quality gateway to give you confidence your commit doesn't break production
* use feature toggles when you don't want the code (yet) to be executed 
   1. this can be as simple as an `if(false)` before the new piece of code you wrote
   2. if you're reading an environment variable or database entry instead you can also switch the new functionality on and off without a deployment
* have a good monitoring and alerting set up

👉 How often are merging something that is deployed to production? Can you increase it to several times per day?


## Trunk based development ➡️

[Trunk based development](https://trunkbaseddevelopment.com/) means working on the main branch only and is needed for CI/CD. Sometimes it's better understood with less ambiguity.

🤓 The word "trunk" originates from version control systems like Subversion which used this word for the main branch.

## Feeling challenged? 💪

Are you doing CI/CD yet? How close can you get to "true" CI/CD? 🤘

⬅️ [Back](/blog)
