# GitHub

## Action runners
We use standard GitHub-hosted runners for CI/CD jobs. Most of our tasks use
Ubuntu-based runners and they should be preferred when action doesn't require
some specific OS/hardware platform. Since in general runners are limited
hardware-wise actions should use the minimal required version of the runner.
As of Dec 2025 this means using ubuntu-slim if possible for the task.

Using "latest" version of runner (and OS respectively) is preferred unless
there are valid reasons to pick any particular one. Usually "latest" is
the most widely available version and actions can't get obsolete because of
missing runners this way and we get more uniformity between different
system components. While theoretically it can bring some instability because
of OS updates practically it's rarely a problem and even some problem happens
we better know it sooner than later.
