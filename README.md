
# prs-blog-post
[Here](https://github.com/superstruct-tech/http_server) is an example repo with a hypothetical HTTP server. This repo has 3 issues (2 open, 1 closed) and 3 PRs that address these issues.

The goal of this material is to show what a PR should look like, common mistakes developers make when creating PRs, and what should be done to prevent from repeating those mistakes.

Take a look at the main bulletpoints in the [Engineering Onboarding Guide](https://github.com/superstruct-tech/onboarding). We're going to match our three PRs with the standards set forth in the Onboarding document to see if they match.
___
### Issue #1

Here is the [first issue](https://github.com/superstruct-tech/http_server/issues/1) in our example repo:
![issue#1](https://i.imgur.com/J0vLpaF.png)

#### Each commit should solve a single problem and be covered by a test that exemplifies that particular feature or fix.

The [PR #2](https://github.com/superstruct-tech/http_server/pull/2) solved this issue. It introduced an endpoint and a test for that endpoint:
![test in PR#1](https://i.imgur.com/MN7mUoG.png)


####  Before a PR is ready for review, make sure that it is a single commit. The exception to this rule is when a PR introduces new packages. Create one extra commit in the same PR for each new package your PR needs.

The PR has 2 commits, which is fine, because one of them introduces `lodash` package:
![commits in PR#1](https://i.imgur.com/TbaBJyX.png)


####  Be sure that your PRs have descriptive titles that explain what has been changed. Use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

This PR used the `feat:` type commit  because it added functionality to codebase. Besides a descriptive title the PR has a description which provides additional information to the teammates who review it:
![title of PR#1](https://i.imgur.com/SR8hJqL.png)
___
### Issue #2

Here is the [second issue](https://github.com/superstruct-tech/http_server/issues/3):
![issue#2](https://i.imgur.com/Rd8nAg9.png)

[PR #4](https://github.com/superstruct-tech/http_server/pull/4) was created to close this issue.


This PR has a couple of problems preventing it from being merged. Let's dive in using the same method: comparing what our PR looks like with what an ideal PR should be.

####  Be sure to connect any PR you are working on to the appropriate issue. Do this via the Zenhub interface and by adding `Closes #X` where X is the issue number to the PR description in Github.

This PR linked issue #2 but the problem is that it won't be closed when PR is merged. The developer didn't link it in the proper way by adding `Closes #X`:
![description to PR#2](https://i.imgur.com/fl7xwc1.png)

We can find his teammate's comment in the Conversation section:
![comment#1 in PR#2](https://i.imgur.com/3vYtXnY.png)


####  Do not mix feature changes (added functionality) with fixes (restored functionality), refactors (no change in functionality), or style changes (only whitespace or other cosmetic changes).

The developer deleted an empty line which could be considerd a minor change but it shouldn't be presented in this PR. Such slight changes could be distracting for reviewers and it could increase reviewing time:

![comment#2 in PR#2](https://i.imgur.com/3Fp3OaE.png)

___
### Issue #3

Here is the [third issue](https://github.com/superstruct-tech/http_server/issues/5):
![issue#3](https://i.imgur.com/Z90c3hH.png)

This issue is linked in the [PR #6](https://github.com/superstruct-tech/http_server/pull/6)

There a few problems which prevent this PR from being merged.

####  Be sure that your PRs have descriptive titles that explain what has been changed. Typically the commit message is sufficient.

This PR has neither a descriptive title nor a description in the comment:
![title in PR#6](https://i.imgur.com/kPUgREY.png)

Here is his teammate's comment which points out that problem:
![comment#1 in PR#6](https://i.imgur.com/cBvp02g.png)

####  Do not mix feature changes (added functionality) with fixes (restored functionality), refactors (no change in functionality), or style changes (only whitespace or other cosmetic changes).

Another problem here is that the developer, along with styling changes, changed functions's names which belongs to in separate refactoring PR.

There are a couple of comments left in the Conversation section informing him about this mistake:
![comment#2 in PR#6](https://i.imgur.com/JPkkpAH.png)

![comment#3 in PR#6](https://i.imgur.com/U1kIwEq.png)
___
## Conclusion
I hope at this point you understand of how crucial it is to follow our [Onboarding Guide](https://github.com/superstruct-tech/onboarding) rules regarding GitHub workflow, code principles, and code style. By following these simple rules you will help your teammates to review your PRs quickly and more efficiently. The chance of missing a bug is also much higher then when you have to review, for instance, a large PR or a PR which introduces different types of changes (e.g. new feature and refactoring). Let's play by the rules and you'll start to have fun very soon.
