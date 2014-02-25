# Participating in Open Source

This guide is for anyone who wants to help contribute to an open source project on GitHub.
First, thanks for your initiative to help out!
One of the reasons that open source is so great is because of the eagerness of others to help.

Whether you've been programming for many years or are brand new, there are a few things you need to know to effectively use GitHub.
There are many guides on "how" to use GitHub from a technical perspective: which buttons to press, what commands to run, etc.
Below I've included some of my favorites.

* [git-it](https://github.com/jlord/git-it) – an interactive tutorial for learning how to use `git` and GitHub
* [GitHub's help page](https://help.github.com/) – find advice on specific topics

Please [tweet](https://twitter.com/briantford) me or file an [issue](https://github.com/btford/participating-in-open-source/issues) if you know of a good addition to this list!

Few guides address "how" you should use it in terms of etiquette, best practices, and expectations.
It can be intimidating to publicize your work on GitHub.
This guide aims to fill in those gaps so you can have some confidence as you enter the open source world.

As you read this guide, please keep in mind that it's okay (and even expected!) to make mistakes.
You don't have to memorize every minute detail.
Just do the best you can and learn as you go.

This guide will assume you are dealing with a JavaScript module installed via `npm` or `bower` that is hosted on GitHub.
Most of the advice is generic for other platforms and languages, but specific commands dealing with `npm` or `bower` probably won't apply.



## Asking a Question

Before you ask, do some searching and reading.
Check the docs, Google, GitHub, and StackOverflow.
If your question is something that has been answered many times before, the project maintainers might be tired of repeating themselves.

If the project is small, it's usually fine to ask questions on GitHub by filing an issue.
If the project is large, they might have a mailing list or IRC channel that would be a better place to ask.
StackOverflow is also a great resource.
Emailing or tweeting at the maintainer(s) might also be a good way to get a question answered, but is generally a worse approach than posting publicly.



## Submitting a Bug Report (or "Issue")

In GitHub, "Bug Reports" are called "Issues."

### Has This Been Asked Before?

Before you submit a bug report, you should search existing issues.
Be sure to check both currently open issues, as well as issues that are already closed.
If you find an issue that seems to be similar to yours, read through it.

If this issue is the same as yours, you can comment with additional information to help the maintainer debug it.
Adding a comment will subscribe you to email notifications, which can be helpful in getting important updates regarding the issue.
If you don't have anything to add but still want to receive email updates, you can click the "watch" button at the bottom of the comments.

### Nope, Hasn't Been Asked Before

If you can't find anything in the existing issues, don't be shy about filing a new one.

You should be sure to include the version the project, as well as versions of related software.
For example, be sure to include the version numbers output by the commands `node --version` and `npm list`.
If you notice that your installed version is not the latest, use `npm update` and confirm that the issue is still there.

Project maintainers really appreciate thorough explanations.
It usually helps them address the problem more quickly, so everyone wins!



## Improving the Code

The best way is to "Fork" the repo on GitHub.
This will create a copy of the repo on your GitHub account.

Before you set out to improve the code, you should have a focused idea in mind of what you want to do.
A commit should do one thing.

As far as code style, just try to imitate the style of existing code.
Don't sweat over this too much.
If the maintainer doesn't like how your code looks, they'll probably give you a few pointers and you can make the changes.

### Forking

TODO: this

`git clone`



### Editing and Testing


Ok, you're ready to start editing the code, right?
Not quite!
Before you start editing, you should create a [branch].
A branch is like an alternate timeline.
You can read more about `git` branches [here].

If you're trying to fix a bug, you might want to name the branch `fix-short-description`.
If you're adding a feature, `feat-short-description` is a good name.

`git checkout -b something`

As you're changing the code, you might want to try it within some app or larger project.

`npm link`,
`bower link`,
or symlinks


Most projects have a set of tests to make sure that the existing functionality of the code stays the same as you make changes.
This helps keep the software stable.

For example, in `npm`.

### Committing and Pushing

`git commit -m "your commit message"`

### Using Your Change

Though it may not be obvious, you can begin using your code in your own projects immediately.



### Getting your Change into the Project

You made your change, tested it, committed it with `git commit`, and want to send it back to the project and have it included in a future version.

To do this on GitHub, you need to submit a "pull request" (PR).

#### Submitting a Pull Request

The golden rule of submitting PRs is to do things the way the project maintainers would want it done.
You can't read the minds of the project maintainers, but you can look what they did in the past.
Considering these things upfront can really help streamlining the process of getting your change accepted.

Simply put: try to immitate the style of the existing code.
Pay attention to the indentation and brace style in the code.
Does the style use or avoid early `return`s?

Code isn't the only thing to take note of.
You should also pay attention to the tense and format of the commit messages.
Some projects prefer commits to be in present tense:

`fixes the bug`

And others prefer past tense:

`fixed the bug`

A good way to check is to use `git log` and read through past commits.

A couple things to keep in mind:

* Don't change the version number of the software (in `package.json` or `bower.json`).
  The project maintainer(s) will take care of this when they decide to release a new version.


If the project is maintained by a corporation, they might have a [Contributor License Agreement (CLA)](http://en.wikipedia.org/wiki/Contributor_License_Agreement) in place to avoid legal issues.


Project maintainers may be busy, so give them some time.
Developers involved in open source often contribute to many projects.
It's not uncommon for a developer to receive dozens of issues notifications a day, so be patient.

If they don't reply in a couple weeks, you might add a comment to "bump" the issue.
Something like "ping @ProjectMaintainer" is usually sufficient.
If you still don't hear from them, an email might be a good way to get in contact.


Assuming the maintainer responds, there are three possible outcomes for your PR:

1. It gets merged. Yay!
2. The maintainer asks you to fix something in the PR before they accept it.
  We'll discuss this below.
3. The PR gets closed, and your change is not added.
  Typically the maintainer will give some justification why.
  If you're adding a feature, maybe there's already some way to get the code to do what you want that you didn't notice.
  If it's a bug, perhaps they want to solve the problem differently.
  Regardless, don't let this discourage you.


#### Fixing Issues in the PR

When asked to make a change to a PR, A common mistake of newcomers to GitHub is to close and create a new one.
There's no need to do this! It's pretty easy to update the existing one.

First, make your changes to the relevant file(s).
As you've done before, stage the file with `git add`:

`git add some-file`

Then you can amend your previous commit like this:

`git commit --amend`

This command takes your staged changes and puts it into your previous commit.

To update the commit in your PR, you'll need to force push:

`git push --force`

The `--force` tells `git` that you want to overwrite the previous commit in your GitHub-hosted repository.

Another common mistake is to create multiple commits instead of amending the changes into one commit.

So you create another commit...

http://git-scm.com/book/en/Git-Tools-Rewriting-History


#### My PR was Closed but I Still Want to use my Changes!

Good news: even if your change isn't accepted into the contributor's repository, you can still use it.

Better yet, you can use your changes while staying up-to-date on the original repo's code.
This is often referred to as "maintaining a fork" of a project.

How does this work?
First, we'll want to add another remote.
Our fork on GitHub has the remote name `origin`.

TODO: note about git remotes
TODO: maintaining a fork (merging "upstream" changes)
TODO: typically there's no reason to publish your fork, you can reference the SHA on github and DL a zip.



## Etiquette

People usually leave communities that seem disrespectful.
In order to make sure everyone feels welcome, it's important to treat everyone with kindness and respect.

Most of the time, this isn't a problem.
Occasionally, developers become frustrated, emotions run high, and feelings get hurt.

Below I've outlined a few common patterns I've seen, as well as steps to mitigate them.

### Assume Everyone is Doing Their Best

> "this problem should be obvious to solve! why hasn't it been fixed?"

Maybe the maintainer has other important things in their life that they need to address.
Prioritizing those things over something on GitHub doesn't make someone lazy.
The health, happiness, and wellbeing of the real person on the other end of the internet is much more important than any bug.

One of the strengths of open source is that you can always fork and fix problems yourself.


> "you obviously don't understand what I'm talking about!"

This type of comment especially drives away beginners.
It should be okay for people to make mistakes.

This is also problematic because it puts the blame on others.
Maybe you could explain the issue better.



It's perfectly normal to get frustrated.
Programming is one of the hardest things people do!
Regardless, it's important to consider the perspectives of others.
Community is more valuable than code, and being nice is more important than being right.


## Conclusion

Thanks for taking the time to read this.
It's my hope this guide will help you get what you want out of open source while at the same time improving it for others.
If you have any suggestions, [please create an issue]().


## License
MIT

![Analytics](https://ga-beacon.appspot.com/UA-48392963-1/btford/participating-in-open-source)
