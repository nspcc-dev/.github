# Project management

We use Github issues to track anything that can/should be done in a project.
PRs are used in a regular way to accept contributions.

## Versioning

Unless specifically noted for a particular project we use semantic versioning
(https://semver.org).

## Milestones

Milestones are used to track a number (usually 2-3) of the next planned
releases with things that are prioritized for them. Issues are attached to
particular milestone by project owners and they can be used to check for
development plans.

Release cycle may vary from project to project depending on the essence of it
and particular needs. Releases are mostly feature-based with no strict time
limits, however a feature can be removed from the release plan if takes more
time to deliver it than originally expected.

## Priorities

We use a multi-dimensional priority system based on urgency/impact/significance
(see more on it in the [labels document](labels.md)). Urgent issues are usually
handled quickly, but most of issues are not urgent, some of them can directly
affect user experience, while some are only visible to developers. Long-term
it's important to have a balance between tasks that deliver most to users in
terms of new features and enhancements and tasks that improve internal quality
of the product. Failing to solve high impact issues means not delivering
anything valuable for users, while failing at highly significant issues means
accruing technical debt, slowing down future developments and increasing the
cost of supporting the code base.

## Assignments

Issues are assigned to a particular person only if they're planned to be
actively worked on. Usually this means that everyone has 1-5 issues assigned
to them at each particular moment. If you have 50 issues assigned to you,
there is something wrong there, you can't be working on all of them at once.
Keeping this relation is important to see the current queue for everyone and
also see what can be taken.

PRs SHOULD NOT be assigned to anyone, author/reviewer roles are sufficient
here.

## PR discussions

They MUST be resolved by the one who started the discussion. PR author MUST
NOT resolve them. This is made to ensure that the solution presented (change
in some commit or additional commit) really satisfies the discussion
creator. It's also a nice natural check list for subsequent review.

## Issue closure

Most of the issues are expected to be closed automatically via "closes XXX" or
"fixes YYY" comments (see [notes on git](git.md) as well). In this cases
issues get a set of corresponding PR/commit links automatically and nothing
special is required. However if an issue is closed manually, there MUST be
a comment describing how and where it's fixed or why it shouldn't/can't be
fixed.

## Documentation

Each project MUST have a README file describing with brief introduction and
minimal instructions on how to use it for what purposes.

Each project that has releases MUST have a release instruction in its documents.

Each project with releases MUST have a CHANGELOG describing changes between
them. This CHANGELOG MUST describe configuration changes if any.

Each project MUST have a LICENSE file with license for its contents.

If project has any runtime dependencies on other projects, there has to be a
table with compatible versions of this project and its dependencies.
