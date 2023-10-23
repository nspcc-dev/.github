# Git

Most of the requirements and technics related to how we use git and manage
repositories are inspired by the Linux kernel development process. If you have
some time take a look at [Linux process documentation](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/process?h=v6.3-rc7).
There is at least one major difference though in that we're using Github
powers for many things (and not sending patches via e-mail).

## New repositories

New repositories should be created only if there is a clear separate
deliverable that doesn't align with other existing repositories. Minimizing
the number of repositories is preferred in general.

## Branches

We're using "master" branch in all our repositories for the main development
line. Releases are made from this branch as well. Some project MAY have
additional branches with legacy or experimental code, but most of them are
expected to have "master" only.

NSPCC members MAY push their new code to branches of the same main repository
or use private repositories (preferred). Branch names SHOULD reflect their
purpose.

Non-private branches MUST be deleted after merge or closure. In general
repositories are expected to only contain master branch if there are no
currently developed ones. Some additional branches MAY be present if they
can't be merged for some reason yet at the same time they have some historical
or other value.

## Commits

The basic unit of any accepted work is a commit (patch). Any work is accepted
as a set of commits to merge into the master branch.

### Logical separation

Separate your changes into logical parts with each part being a separate
commit that solves exactly one problem that is outlined in the commit message.
One issue often requires a number of changes to solve it, they SHOULD be
committed separately.

### Whitespace changes

Any non-functional whitespace changes MUST NOT be mixed with normal ones that
change the behavior. Either drop them or make a separate commit doing just
that.

### Technical correctness

Ensure that each package you're modifying can be compiled and works (passes all
unit tests) at every commit. This is important to have an ability to bisect
problematic changes if there is a need to.

### Commit messages

The following format is expected:

  subsystem: short description (up to 80 symbols, better up to 60)

  Long description with references, links, test data and whatever else is
  needed to explain what, why and how is changed (use up to 80-character
  columns for word-wrapping, any attachment like an application log,
  external link, utility output is an exception). It should consist of
  sentences (or a single sentence) that follow at least some basic
  punctuation/grammar rules, e.g. start with a capital letter and end
  with a period.

  Signed-off-by: Your Name <email@example.com>

In rare cases commits touch a number of subsystems, these SHOULD have "*:"
prefix. In even more rare cases there are no real subsystems in a (small)
repository, in this case the subsystem prefix MAY be omitted.

If commit fixes some issue it MUST be mentioned in the message using "fixes
XXX" (or "closes XXX") notation to automatically close the respective issue.

Description MUST contain enough data to understand what's going on without
looking at the linked issues (they're additional data, not the primary thing
wrt git log). Commits with messages like "fix" or "cleanup" MUST NOT be
merged.

#### Developer certificate of origin

Read carefully and sign-off your commits with [DCO](https://developercertificate.org/).
Engineering department doesn't know why it's important, but it is.

## Merges

We use merge commits by default because it's safer (compared to rebasing which
can lead to errors in rare cases), more logically correct (there was a branch
and there it is in git history), allows to group changesets and have some
unifying message for all of them. Squashed merging leads to loss of
information about individual logical changes. Rebased patchsets lead to linear
history where it's harder to see relations between individual patches.

Merging a set of changes means that all commits from it will be present in the
project's log, which in turn means that all patches presented for a merge MUST
be functional. If there is a need to fix something in the code based on review
results most of the time it's done via changing existing patches and
force-pushing the result.

Merged branches MUST have no conflicts with the current master. If there are
any conflicts author is expected to fix them by rebasing and force-pushing the
branch.
