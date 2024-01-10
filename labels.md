# Labels

Each repository has a set of labels used for task management purposes.
We have a set of organization-specific labels used by every repository and at the
same time each particular repository can define a set of labels of its own based
on project-specific needs. All of them need to be described in appropriate
documents to synchronize on their meaning and usage patterns.

Forked repositories that are not expected to be maintained for a long time
(for example, created to add NeoFS support into some product and likely to be
deleted after the merge to upstream) can inherit labeling scheme from the
original project and not be converted into NSPCC one.

## Categories

### Type

- bug

  There is some unexpected behaviour in already existing functionality.

- discussion

  An open discussion of some problem to explore better ways to deal with it,
  not necessarily something that should/can be done.

- enhancement

  Some existing functionality should be improved to allow for more use cases.

- feature

  A completely new functionality is needed.

- task

  Generic task not resulting in any direct product improvements like
  performing some specific test and posting the results.

- question

  An open discussion that is not specifically dealing with some known problem.

- epic

  A collection of other interrelated tasks.

### Priorities

There are three priority categories that quantify different aspect of a
particular issue. See more in [project management document](project-management.md).

- Urgency

  Specifies how urgent is an issue based on how serious and immediate are
  consequences of this issue not being resolved. This scale is mostly about
  time parameters.

  * U0

    Needs to be resolved immediately, negative impact can be felt within days.
    For example, some issue making mainnet operation impossible.

  * U1

    Critically important, negative impact in one-two weeks. Examples are a bug
    affecting some mainnet functions or a regular security issue.

  * U2

    Serious, negative impact in one-two months. Like some function that is
    planned to be demonstrated at a conference.

  * U3

    Normal, negative impact in ~six months. Regular feature implementation or
    bug fix.

  * U4

    Minor, negative impact in 1+ years or none at all. Used for random
    enhancement ideas or technical debt.

- User impact

  Specifies how visible this issue is for users and how it can or can't affect
  using the product for them. This scale mostly relates to value the project
  delivers to its users.

  * I0

    Extensive, can't be unnoticed. Changing the service configuration
    completely or radically changing user experience in multiple widely used
    functions.

  * I1

    High, noticed by most of users. Seriously improving performance or
    redesigning UI.

  * I2

    Regular, noticed by users of some particular subsystem or feature.
    Implementing some new function.

  * I3

    Minimal, only noticed in some specific cases. An additional setting in
    already existing functions.

  * I4

    No visible changes. Code refactoring and alike.

- Technical significance

  Specifies strategic technical influence of this issue, how far-reaching are
  consequences of solving it. This scale is used for representing internal
  understanding of how something can or can't affect our ability to build more
  things on top of current code base and support it.

  * S0

    Critical, affects whole product. New static analysis for all codebase.

  * S1

    High, affects a number of components or subsystems. Changing some important
    dependency.

  * S2

    Regular, affecting some component. Refactoring some module.

  * S3

    Minimal, affects some local code. Implementing a new function.

  * S4

    Routine, affecting nothing. Fixing some bug.

### Special

- blocked

  The issue can't be immediately solved, either it depends on another issue or
  waits for some additional external input (this MUST be specified in the
  comment when this label is added). The label represents issue state and is
  therefore dynamic, can be added/removed when appropriate.

- config

  Any problem/PR that affects config format MUST have it.

- dependencies

  This one is used automatically by Dependabot, but can be applied to manual
  PRs or issues as well if they're dealing with project dependencies somehow.

- documentation

  Used for issues that only (or mostly) require some documentation changes.

- \<language\>, like "go" or "python"

  We use "go" In repositories containing Go code for any Go-specific
  refactorings usually associated with a new version of the standard library.
  Similar tags can be used in non-Go repositories for language-specific
  refactorings.

- good first issue

  This one is important for Github to be able to offer some entry-level
  problems that are good for the beginners in a particular project.

- help wanted

  This one is also Github-specific and allows to signify issues that are not
  likely to be resolved by NeoSPCC team, external contributors are encouraged
  to tackle them.

- performance

  Anything affecting performance metrics.

- security

  Anything dealing with security.

- test

  Issues about unit tests, this label is not used in testcase repositories.

## Coloring style

Each category has some associated color that is used for all labels in this
category. Priority labels are a bit different in that they're using a set of
similar colors to signify particular priority.

## Naming style

In general, lowercase, single-word labels are preferred. But there are ones that
are treated specially by Github and they're used as is, for example "good first
issue" and "help wanted".

## Persistence

Most of labels are intended to be sticky, once defined they're not likely to
change. But since Github's project management abilities are limited, some can
substitute task state/relation fields and therefore be more dynamic, added and
removed as appropriate.
