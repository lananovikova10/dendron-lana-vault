---
id: h9vb9j271i83oricupmc2vz
title: Styleguides
desc: ''
updated: 1666386257800
created: 1665419192923
---

- http://styleguides.io/
- https://redhat-documentation.github.io/supplementary-style-guide/
- [A curated style guides collection by Barrie Byron](https://github.com/barriebyron/techcomm/blob/main/styleguide/style-guide-collection.md)


github.com/cobalthq/cobalt-product-public-docs

own styles on project level
/styles
shell script in bin runs and sets up vale for the first time
https://gist.github.com/tarasweeney/da0ed4385db342f06a8f2e46c14f38df

Are updates are applied in vale?
As Google styleguide updates a lot

What styleguides or rules do you miss in Vale packages?
Vale recently have introduced packages feature with makes it kind of a marketplace, can you you dream what styleguides or rule sets do you miss in Vale packages? Maybe for specific markup languages

linkedin.com/pulse/automate-style-checks-tara-english-sweeney/

We use vale and markdown linting in VSCode and in our CI Pipeline. One is good for hints while editing the documentation and one is good for QA checks when files are comitted.

How extencive of a type of rule you can write?

how do you set up exceptions to rules? wondering how best to incorporate with docs that are a heavy mix of code examples and text

valentjn.github.io/ltex/

Only seems to run in github for the first commit

GoodDocs - automatec styleguide

Here's our repo that uses Vale: github.com/Datadog/documentation

github.com/thegooddocsproject/templates/tree/dev/style-guide

Lana Novikova•20:30
I've recently found a bunch of Vale rules for Legal domain github.com/PureLegalTech/LegalRules So things are getting serious))) Layers are going there)

Bryan Klein•20:31
We have found Vale, Markdown linting and spelling/grammar checking in the IDE is more useful than having it all run as a check after the errors are made and committed.

You can run it locally to have control, but not in the pipeline
Not ready to put it into commit check process

Junior writers get familiar with the style guide

Self check, even if you don't know style guide like 100 percent, it can check you

Peoole will learn the styles by running it

Bryan Klein•20:33
I added these extensions to the GitPod config file (yml) so that every editor gets the same environment, rules and tools wherever they are editing.

User avatar
Erin Moore•20:33
I've found the same for myself, anecdotally, Bryan. Unless the pipeline-level linting is an error-level blocker, it's much easier to address in VSCode.

The squiggly underlines are much louder, visually.

I'm interested in CI/CD linting because I get docs contributions from folks who aren't technical writers. Usually I edit their work first, but not always. (Would be nice to have something flag issues for me.)

- The question of whether to include style checks into the release process is yet to discuss and depends on the working culture you have.
- Most of the participants agreed that checking against style guide in the IDE/locally or on commit is less invasive and also effective as checks are made before the errors are made and committed
- Automated styleguides help junior writers/newcomers to adapt quicker, they learn seeng these warnings appear.
- If you have the external contributors who are not always TW, automated checks on CI/CD level make more sense
- Nice practice mentioned is to use GitPod config file (yml) so that every editor gets the same environment, rules and tools wherever they are editing.

Cameron Shorter•20:35
Q: Has anyone used Value for managing Glossaries?

User avatar
Cameron Shorter•20:35
... And popup definitions for glossary term

Dave May'

shortcode to each term

Schema
structured data about everytgig