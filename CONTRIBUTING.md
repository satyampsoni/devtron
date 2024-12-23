# How to Contribute

Devtron is [Apache 2.0 licensed](LICENSE) and accepts contributions via GitHub
pull requests. This document outlines some of the conventions on development
workflow, commit message formatting, contact points and other resources to make
it easier to get your contribution accepted.

We gratefully welcome improvements to issues and documentation as well as to code.



## Communications

The project uses discord for communication:

To join the conversation, simply join the **[discord](https://discord.gg/jsRG5qx2gp)**  and use the __#contrib__ channel.




### Contribute Helm Charts

[Contribute your helm charts](https://github.com/devtron-labs/devtron/tree/main/contrib-chart) for the devtron community for upcoming `community charts` feature



# Contributing Guidelines

Devtron accepts contributions viaGitHub issues and pull requests. This document outlines the process
to how you can contribute to Devtron.

## Reporting a Security Issue

Most of the time, when you find a bug, it should be reported using [GitHub
issues](https://github.com/devtron-labs/devtron/issues). However, if you are reporting a _security
vulnerability_, please email a report to
[]). This will give us a
chance to try to fix the issue before it is exploited in the wild.

## Support Channels

Whether you are a user or contributor, official support channels include:

- [Issues](https://github.com/helm/helm/issues)
- Discord:
  - User: 
  - Contributor: 

Before opening a new issue or submitting a new pull request, it's helpful to search the project -
it's likely that another user has already reported the issue you're facing, or it's a known issue
that we're already aware of. It is also worth asking on the Slack channels.

## Contributions we expect you to make

There are 5 types of contributions that we expect from you.

- `question/support`: These are support or functionality inquiries that we want to have a record of
  for future reference. Generally these are questions that are too complex or large to store in the
  Slack channel or have particular interest to the community as a whole. Depending on the
  discussion, these can turn into `feature` or `bug` issues.
- `proposal`: Used for items (like this one) that propose a new ideas or functionality that require
  a larger community discussion. This allows for feedback from others in the community before a
  feature is actually  developed. This is not needed for small additions. Final word on whether or
  not a feature needs a proposal is up to the core maintainers. All issues that are proposals should
  both have a label and an issue title of "Proposal: [the rest of the title]." A proposal can become
  a `feature`.
- `feature`: These track specific feature requests and ideas until they are complete. They can
  evolve from a `proposal` or can be submitted individually depending on the size.
- `bug`: These track bugs with the code
- `docs`: These track problems with the documentation (i.e. missing or incomplete)

  ### Issue Lifecycle

The issue lifecycle is mainly driven by the maintainers, but is good information for those
contributing to Devtron. All issue types follow the same general lifecycle. Differences are noted
below.

1. Issue creation
2. Triage
    - The maintainer in charge of triaging will apply the proper labels for the issue. This includes
      labels for priority, type, and metadata (such as `good first issue`). The only issue priority
      we will be tracking is whether or not the issue is "critical." If additional levels are needed
      in the future, we will add them.
    - (If needed) Clean up the title to succinctly and clearly state the issue. Also ensure that
      proposals are prefaced with "Proposal: [the rest of the title]".
    - We attempt to do this process at least once per work day.
      
3. Discussion
    - Issues that are labeled as `feature` or `bug` should be connected to the PR that resolves it.
    - Whoever is working on a `feature` or `bug` issue (whether a maintainer or someone from the
      community), should either assign the issue to themselves or make a comment in the issue saying
      that they are taking it.
    - `proposal` and `support/question` issues should stay open until resolved or if they have not
      been active for more than 30 days. This will help keep the issue queue to a manageable size
      and reduce noise. Should the issue need to stay open, the `keep open` label can be added.
4. Issue closure

### PR Lifecycle

1. PR creation
    - PRs are usually created to fix or else be a subset of other PRs that fix a particular issue.
    - We more than welcome PRs that are currently in progress. They are a great way to keep track of
      important work that is in-flight, but useful for others to see. If a PR is a work in progress,
      it **must** be prefaced with "WIP: [title]". Once the PR is ready for review, remove "WIP"
      from the title.
    - It is preferred, but not required, to have a PR tied to a specific issue. There can be
      circumstances where if it is a quick fix then an issue might be overkill. The details provided
      in the PR description would suffice in this case.
2. Triage
    - The maintainer in charge of triaging will apply the proper labels for the issue. This should
      include at least a size label, `bug` or `feature`, and `awaiting review` once all labels are
      applied. See the [Labels section](#labels) for full details on the definitions of labels.
    - Add the PR to the correct milestone. This should be the same as the issue the PR closes.
3. Assigning reviews
    - Once a review has the `awaiting review` label, maintainers will review them as schedule
      permits. The maintainer who takes the issue should self-request a review.
    - PRs from a community member with the label `size/S` or larger requires 2 review approvals from
      maintainers before it can be merged. Those with `size/XS` are per the judgement of the
      maintainers. For more detail see the [Size Labels](#size-labels) section.
4. Reviewing/Discussion
    - All reviews will be completed using GitHub review tool.
    - A "Comment" review should be used when there are questions about the code that should be
      answered, but that don't involve code changes. This type of review does not count as approval.
    - A "Changes Requested" review indicates that changes to the code need to be made before they
      will be merged.
    - Reviewers should update labels as needed (such as `needs rebase`)
5. Address comments by answering questions or changing code
6. LGTM (Looks good to me)
    - Once a Reviewer has completed a review and the code looks ready to merge, an "Approve" review
      is used to signal to the contributor and to other maintainers that you have reviewed the code
      and feel that it is ready to be merged.
7. Merge or close
    - PRs should stay open until merged or if they have not been active for more than 30 days. This
      will help keep the PR queue to a manageable size and reduce noise. Should the PR need to stay
      open (like in the case of a WIP), the `keep open` label can be added.
    - Before merging a PR, refer to the topic on [Size Labels](#size-labels) below to determine if
      the PR requires more than one LGTM to merge.
    - If the owner of the PR is listed in the `OWNERS` file, that user **must** merge their own PRs
      or explicitly request another OWNER do that for them.
    - If the owner of a PR is _not_ listed in `OWNERS`, any core maintainer may merge the PR.

#### Documentation PRs

Documentation PRs should be made on the docs repo: . Keeping documentation up to date is highly desirable, and is recommended for all user facing changes. Accurate and helpful documentation is critical for effectively communicating behavior to a wide audience.

Small, ad-hoc changes/PRs to Devtron which introduce user facing changes, which would benefit from documentation changes, should apply the `docs needed` label. Larger changes associated with a HIP should track docs via that HIP. The `docs needed` label doesn't block PRs, and maintainers/PR rviewers should apply discretion judging in whether the `docs needed` label should be applied.

### sign the work

### Developer's task
If you are planning to build or develop something, we encourage you to refer to the Developer's Guide for detailed instructions and best practices.

### Code Structure and practices 
Devtron has following components

- [devtron](https://github.com/devtron-labs/devtron.git) main co-ordinating engine
- [git-sensor](https://github.com/devtron-labs/git-sensor.git) microservice for watching and interacting with git
- [ci-runner](https://github.com/devtron-labs/ci-runner.git) Devtron runner for executing jobs
- [guard](https://github.com/devtron-labs/guard.git) A kubernetes validating webhook for policy inforcement
- [imge-scanner](https://github.com/devtron-labs/image-scanner.git) microservice for docker image vulnerability scanning
- [kubewatch](https://github.com/devtron-labs/kubewatch.git) microservice for k8s event filtering and recording 
- [lens](https://github.com/devtron-labs/lens.git) microservice for performing analytical task
- [dashboard](https://github.com/devtron-labs/dashboard.git) UI for devtron written in react js

## Certificate of Origin

By contributing to this project you agree to the Developer Certificate of
Origin (DCO). This document was created by the Linux Kernel community and is a
simple statement that you, as a contributor, have the legal right to make the
contribution. No action from you is required, but it's a good idea to see the
[DCO](DCO) file for details before you start contributing code to Devtron.





