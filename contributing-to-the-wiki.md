# Contributing to the Wiki

We're always looking for contributors to help get the wiki updated and in tip top shape. As of 7/10/25, if you've found something missing, outdated or incorrect, you can help us improve the Wiki by editing it directly on GitHub! This page explains how to get started and make your first contribution.

{% hint style="success" %}
**This guide assumes you have little to no experience with GitHub**

For experienced folk, you can skip the explanation and simply [fork and edit the repo](https://github.com/vibecentralmc/wiki) as usual, then create a PR.
{% endhint %}

## Step 1 - Access the wiki repository on GitHub

First, head over to the GitHub website and [create an account or login](https://github.com/) if you haven't yet. A GitHub account is required to propose edits.

Once you're logged in, you can head over to the Wiki repository at [https://github.com/vibecentralmc/wiki](https://github.com/vibecentralmc/wiki). This official repository page shows all the Wiki's most up-to-date page files and assets that are displayed nicely here on the GitBook frontend.

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Step 2 - Create a fork of the repository

A "fork" on GitHub is a personal copy of a repository. Your fork is a working copy of the wiki where you'll make all your proposed edits.

To create your fork, simply hit the "Fork" button on the top right of the repository (see image above).

Your created fork of the wiki will live at _https://github.com/**`yourname`**/wiki_

Even for multiple contributions over time, you'll always use the same fork. GitHub provides options (as outlined below) to sync your fork with the latest updates from the main repository as needed.

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

You can ensure you're on your fork by looking at the top - note how it says "forked from vibecentralmc/wiki".

### Understanding up to date status

Note the section near the top that shows "This branch is up to date with vibecentralmc/wiki:main". This means that both the official wiki repository and your fork are currently identical. As you or others make changes, this status will update. For example:

* "This branch is 3 commits ahead of vibecentralmc" means you have made and saved three changesets/commits to your fork that are not yet in the official wiki.
* "This branch is 1 commit behind vibecentralmc" means the official wiki has one changeset/commit that your fork doesn't yet have, and you'll need to sync your fork to get it using the "Sync fork" button.

### **Understanding commits**

In version control systems like Git, which are often used for codebases and other collaborative projects like wikis, a 'commit' or 'changeset' is essentially a group of one or more edits you made to the project at a specific point in time. You can think of it like saving a document and taking a snapshot of just those changes.

* **On GitHub, when you 'commit' changes,** you're packaging up a set of all your most recent changes since your last commit (like adding a new sentence, fixing a typo, etc.) and giving it a brief name & description of your primary changes, like "Fix typo in rules page" or "Create Skills page".
* **In GitHub, each commit builds on the previous one,** creating a chronological history of all edits to the project. This ensures everything is tracked and can be reverted or referenced if needed. You can explore all the commit history by clicking on "commits" in the top right of the project, and even browse the entire repository as a snapshot when a specific commit was made.

## Step 3 - Make your contributions in your fork

The Wiki pages use markdown formatting, similar to Discord. For example, you can bold text by surrounding it with two asterisk like `**this**` .

A large majority of the markdown that will be helpful to know can be learned at:

* [https://gitbook.com/docs/creating-content/formatting/markdown](https://gitbook.com/docs/creating-content/formatting/markdown)&#x20;
* [https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/)

But for most purposes, you should be able to get the gist of it by just looking at existing pages on GitHub for reference and comparing their raw markdown and their rendered previews.

{% hint style="info" %}
GitBook also uses special formatting and tokens to represent things like hint boxes (the box this text is in), that GitHub does not support rendering in previews.

You shouldn't worry or bog yourself down about the complex formattings and just focus on the content and accuracy of your contributions. Any special formattings can be added by staff later on - the content itself is what matters the most!
{% endhint %}

**Now all that's left to do is find what you want to edit or add!**

### Editing an existing wiki page

You can find Table of Contents and quickly navigate to any existing wiki page by opening the `SUMMARY.md` file which is at the bottom of the repository page in the files section (highlighted in red):

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Once you open the page you'd like to edit, you'll see its preview opened. Hit the edit button in the top right to make it editable (highlighted in red).

<figure><img src=".gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

Now you can freely edit the page's markdown! Swap between "edit" and "preview" at the top left to see the rendered view of the page.

<figure><img src=".gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

After you've made edits, hit the green "commit changes" button in the top right and explain your changes. This will commit your edits to **your fork only** of the repository.

You can continue editing files like this and creating commits in your repository until you're ready to submit the changes to be merged into the live wiki.

### Creating a brand new wiki page or section

To create a new wiki page or section, navigate to the section where you'd like it to be, (ex. in the "survival" folder/section) and use the "Add file" button at the top right. Remember to name pages with the ".md" file extension!

{% hint style="success" %}
**Copy and paste the new wiki page template below to get a solid base to work from for adding new pages.**

**All pages should follow this basic starting format, including the page title, description, and section headings with subheadings with respective empty lines.**
{% endhint %}

```markup
# Page Title

A short description explaining what the feature is that this page is about

## Section Heading

Section content

### Section subheading

## Another Section Heading

Section content, with a list!
* Bullet point item 1
* Bullet point item 2
```

## Step 4 - Submit your contributions to be merged into the live Wiki

When you're ready to submit your changes to the official wiki live at [https://wiki.vibecentral.xyz](https://wiki.vibecentral.xyz/), head back to your fork's main page at _https://github.com/**`yourname`**/wiki_ and click the "Contribute" button, then "Open Pull Request"&#x20;

<figure><img src=".gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

On the pull request page, just add a title and write a description of your changes, then hit "Create pull request". None of the options at the top need to be adjusted :)&#x20;

When you create a pull request/PR, you're submitting your changes from your personal working copy / fork of the wiki to be merged or "pulled" into the official, main version.

PRs also serve as dedicated conversation threads. Staff members can reply in your PR to ask questions about your changes or request further edits if needed. If everything looks good, has no merge conflicts, and meets the wiki's standards, staff will approve your PR! Once approved, all your changes will be merged into the live wiki within minutes.

And that's it! Thank you for taking interest in contributing to the wiki, seriously, you're awesome!!

{% hint style="success" %}
We recommend hitting the "Watch" button in your PR to ensure you receive email notifications for any activity in it.

It's also recommended to Create a Ticket on our Discord to allow for easier communication regarding your PR. If it's your first PR, you can also request your Wiki Contributor badge in Discord once your PR is accepted!
{% endhint %}

## Have any questions or need any help with anything?

Just reach out! Using tickets on our [Discord](general/discord.md) are the best way to get into contact with server staff. Your contributions are greatly valued <3
