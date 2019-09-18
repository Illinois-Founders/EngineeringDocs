# How Founders Uses Git:

## Command Line Interface 

Get comfortable using the CLI for working in Git. Not only is it much more efficient than using the graphical interface through theWeb UI, but it'll give you a better understanding for how Git works under-the-hood in the long run. Of course, the CLI isn't the best option for everything you'll need to do in Git / Github -- so use your discretion to determine the best use case. 

## Commits are Atomic 

We think of commits as being atomic:

> atomic: of or forming a single irreducible unit or component in a larger system. 

This means that we want to make commits that are small and self-contained: an irreducible feature, fix, or code imrpovement. We should commit things that are logically coherent chunks that contribute to somelarger feature or build. 

### Commit Early and Often

When working on a feature from scratch or a fix to a problem - we should always:

1. Lay the groundwork by designating clearly defined small checkpoints along the way. 
2. Work to complete check-points one-by-one: a completed check-point is a commit. 

Git only takes responsibility for saving your changes once you make a commit (or at the very least `git add`), it's important that we plan out check-points and `git commit` once we hit them along the way. 

### Write Proper Commit Messages 

A commit message should explain what was added or what was changed to our codebase, and *why*. We don't use commit messages to explain implementation (that's what good code documentation is for!). We _do_ use commit messages to establish the following: 

* Why is it necessary? 
* How does this address an issue or contribute to development of a feature?
* What effects will this commit have? 

Commit messages should be written in the imperative: "Fix some issue" not "Fixed an issue". Commit messages should reflect what _will_ happen when it gets merged into our codebase. 

To write a commit message:

`git commit -m "A commit message"` 

If it can be explained sufficiently in 50 characters, use the above approach. If not:

`git commit` 

Will open your default text editor. Keep the first line to 50 chracters as a subject, skip a line, and then explain the rest of the necessary details. 

## Our Git Workflow: Feature Branching

Our philosophy around how we develop using Git / Github can be deduced from this concept of *Feature Branching*. Instead of committing directly to the `master` branch, we work on separate branches dedicated to some specific development task. This enables multiple developers to work on interconnected features (or the same feature) without interacting directly with the main code base. 

The main advantages to this workflow are:
1. `master` should never contain broken code
2. Any developer can get entire up-to-date codebase with ease
3. It enables a clear process for code review and continuous integration 

### Here's how it works:

#### We start with the `master` branch:

`git checkout master` 

`git fetch origin` 

`git reset --hard origin/master` 

We set our current branch to `master`. Pulled in the latest commits and reset our local repo's copy of master to the latest version.

#### Create a new branch:

Say we're working on some arbitrary feature, let's create a separate branch to work on that:

`git checkout -b new_feature`

We created a new branch called `new_feature` and checked it out. 

#### Add to tracking, commits, and pushing changes

As you work on this feature and get to logical check-points along the way, we can make commits and push changes by doing the following:

`git status`
`git add <file>`
`git commit -m "a useful commit message"`

We've added the files we want to track and committed them, we can push this changes up to the remote now:

`git push -u origin new-feature` 

(After you've set the remote with `-u` by running this command the first time, you can simply use `git push`)

This pushed our changes on this feature branch up to our central repository. We will continue to push commits up to the remote until we've completed the necessary work to call this feature "complete." When there's nothing left to commit, make a pull request to merge this feature branch into master. 

## Pull Requests 

Pull requests are the mechanism that we use to review code before merging it into our code base. Pull requests (PR's for short), present an opportunity to review some developed code - typically for a specific feature or patch before we allow this to be merged into `master`. 

Once you've completed all the necessary work on the `feature` branch, create a PR to kick-off the review process for the work you just completed. 

### PR Template 

In all of our repository's root directory, you'll find a file titled `PULL_REQUEST_TEMPLATE.md`. Every time we create a PR, we need to fill this template out in its entirety - this is the layer of information that is being passed on to those who will be reviewing your code, so it's essential that we brief them appropriately on the work we completed. 

### Reviewers 

On every PR, we specify someone on the team that will review the code we've written. This should be someone with proficiency in the language that the code has been written in and that has a sufficient understanding of the feature / problem that is being developed for. Reviewers will review the code, leave comments / suggestions, and communicate feedback to the PR owner. *Reviewers are responsible for ensuring that the changes referenced in the PR are correct and up to all of our code standards.* 

### Assignes

Assignes are people who should know about the PR, but who's approval is not required to merge this code into the codebase. Most often, Assignes are those that you're developing alongside or that are dependent on the PR in question getting through to our codebase. 
