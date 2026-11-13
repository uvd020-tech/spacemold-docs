---
title: Privacy Policy — SpaceStamp
---

{% raw %}

# Privacy Policy

**App:** SpaceStamp

**Last updated:** 13 November 2026

[← Documentation home](index.html)

## Summary

SpaceStamp is an [Atlassian Forge](https://developer.atlassian.com/platform/forge/)
app. It runs on Atlassian's infrastructure. It has no servers of its own, makes
no requests to other hosts, and sends no data to any third party. What the app
stores stays inside the Forge platform and your Confluence site.

The app declares no external permissions in its manifest (no egress), which
makes this verifiable rather than a promise.

## What the app stores

When an administrator saves a template, the app stores it in Forge storage:

| Data | Why |
| --- | --- |
| Template name, source space key, the copy settings | To create spaces from the template |
| Template ID, the time it was created and last changed | To find the template and keep its dates |

When someone starts a copy, the app stores a copy job in Forge storage:

| Data | Why |
| --- | --- |
| The Atlassian account ID of the person who started it | To run the copy as that person and to limit who can view the job |
| Template ID, source space key, name and key of the new space, the copy settings | To run the copy |
| The values of `{{Project}}`, `{{Owner}}` and `{{today}}`. `{{Owner}}` is the person's display name unless they change it | To replace the variables |
| IDs of spaces, pages and folders, titles of pages and folders | To track the copy. The list of page trees is cleared after the pages are copied |
| Role assignments of the source space: principal type and ID, role ID | To repeat them in the new space. Each one is removed from the list once it is handled; failed ones stay in the report |
| Status, counts, titles of items not copied or not updated, error text | To show progress and the report |

Values of variables are whatever the person typed, so they may contain any text
the person chose to enter.

The person's browser keeps the ID of their last job in local storage, so that
the progress screen survives a page reload.

The app does **not** store passwords, email addresses, payment details, or the
text of pages. It reads page text to replace variables, and does not keep it.

## What the app reads from Confluence

Using the permissions of the person who is using the app or who started the
copy:

- the person's display name, and whether they administer Confluence;
- the spaces visible to the person;
- the source space: its name, key and description, its pages and folders, and
  the items in its page tree;
- titles and text of the pages in the new space;
- the number of attachments of the pages, for the report;
- the role assignments of the source space, if the template copies space roles.

## What the app writes to Confluence

All of this goes to the new space, with the permissions of the person who started
the copy:

- the space itself;
- copies of pages, with attachments, labels and restrictions if the template
  copies them;
- folders;
- changed titles and text of the copied pages (variables and links);
- role assignments, if the template copies space roles.

The app does not change the source space or any other existing space.

## Logs

The app's code writes nothing to Forge logs and nothing to the browser console.

## Analytics and tracking

The app contains no analytics, no tracking pixels, no advertising and no
third-party scripts. It does not profile users and makes no automated decisions
about them.

## Data retention and deletion

- Deleting a template removes it from Forge storage. Spaces created from it stay.
- Copy jobs are stored with an expiry of 30 days after their last change.
- Uninstalling the app removes its stored data according to Atlassian's Forge
  storage lifecycle. On a development installation on 6 November 2026 templates
  and jobs were gone after uninstalling and installing again.
- Spaces created by the app are ordinary Confluence spaces. They stay after
  uninstalling.
- To request deletion of data associated with your site, contact us at
  [info@vudia.site](mailto:info@vudia.site).

## Where data is stored

In Forge's storage, operated by Atlassian, and in your Confluence site. Hosting
location and residency follow the Atlassian Cloud infrastructure your site runs
on. See the [Atlassian Trust Center](https://www.atlassian.com/trust) for
details.

## Your rights

Since the app processes data on behalf of your organisation, requests for
access, correction or deletion of personal data are best raised with your own
Confluence administrator, who controls the site. We will assist administrators
with any such request — contact [info@vudia.site](mailto:info@vudia.site).

## Changes to this policy

Material changes will be published on this page with an updated date above.

## Contact

Vudia — [info@vudia.site](mailto:info@vudia.site)

---

[← FAQ](faq.html) · [Documentation home](index.html) · [Security →](security.html)

{% endraw %}
