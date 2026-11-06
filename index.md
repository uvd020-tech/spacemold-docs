---
title: Spacemold — Documentation
---

{% raw %}

# Spacemold

Spacemold creates new Confluence spaces from a space you keep as a sample. A
Confluence administrator saves a space as a template. Anyone who opens the app
can then create a new space from it, with `{{Project}}`, `{{Owner}}` and
`{{today}}` replaced in page titles and text.

The app is built on [Atlassian Forge](https://developer.atlassian.com/platform/forge/)
and runs on Atlassian infrastructure. It declares no external permissions — see
the [Privacy Policy](privacy.html).

---

## Quick start

**Create a template (Confluence administrators):**

1. Open **Apps → Spacemold**, then the **Templates** tab.
2. Click **New template**.
3. Enter the **Template name** and choose the **Source space**.
4. Tick what to copy: **Attachments**, **Page labels**, **Page restrictions**,
   **Space roles**, **Space description**.
5. Click **Save**.

**Create a space:**

1. Open **Apps → Spacemold**. The create form opens first.
2. Choose the **Template**, then enter the **Space name** and the **Space key**.
3. Change the values for `{{Project}}` and `{{Owner}}` if you need to.
4. Click **Create space**. The screen shows each stage of the copy.
5. When the copy ends, read the report and click **Open space**.

The copy goes on if you close the page. The app shows it again when you come
back in the same browser.

In our tests on one Confluence site, a space of 23 pages took under 8 minutes
(7 November 2026). A space of 261 pages, all of them directly under the home
page, took about 24 minutes (5 November 2026).

## What goes into the new space

| Content | What happens |
| --- | --- |
| Home page | Copied over the home page of the new space. Its title is the space name, or `<space name> Home` if a page of the source space already has that title |
| Pages | Copied with their child pages |
| Pages outside the tree of the home page | Placed under the new home page |
| Folders | Created again in the new space, with their pages inside |
| Attachments, page labels, page restrictions, space roles, space description | Copied if ticked in the template |
| Links that name the source space by its key | Changed to the new space |

The [FAQ](faq.html#what-is-not-copied) lists what is not copied.

## Variables

Write a variable in a page title, a folder title or page text of the source
space:

| Variable | Replaced with |
| --- | --- |
| `{{Project}}` | The value entered in the form. If it is empty, the space name |
| `{{Owner}}` | The value entered in the form. The form suggests your name |
| `{{today}}` | Today's date in your browser, as `YYYY-MM-DD` |

- Spelling and case must match exactly.
- If the value is empty, the variable stays in the text as it is.
- A value can be up to 200 characters long.

## Who can do what

| You are | You can |
| --- | --- |
| Confluence administrator | Create, edit and delete templates, create spaces from them |
| Anyone who opens the app | See the template list, start a copy and follow their own copy. Confluence decides whether they can create a space |

The copy runs with the permissions of the person who started it. The app checks
who can change templates on the server, for every change.

## Limits

- A source space can have up to 5000 pages.
- Its home page can have up to 1000 child pages.

## Documentation

| Page | What it covers |
| --- | --- |
| [FAQ](faq.html) | What is not copied, variables that stayed in the text, a copy that stopped |
| [Privacy Policy](privacy.html) | What is stored, read and written |
| [Security Policy](security.html) | Architecture, permissions, vulnerability reporting |
| [Support](support.html) | How to reach us and what to include |

{% endraw %}
