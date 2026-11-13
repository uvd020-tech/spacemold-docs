---
title: FAQ — SpaceStamp
---

{% raw %}

# FAQ

[← Documentation home](index.html)

## What is not copied?

- Blog posts, the space logo and the look of the space.
- Whiteboards, databases and embeds. Those directly under the home page or in a
  folder are listed in the report under **Items that cannot be copied**. Those
  placed deeper in a page tree are not listed, so check them by hand.
- Pages that the person who started the copy cannot see.

Not tested yet: page comments, folders at the root of a space, and sites without
space roles.

## Why are some pages missing from the copy?

The copy runs with the permissions of the person who started it. Pages closed to
that person do not reach the copy, and the report does not count them in the
expected number either. Ask someone who can see those pages to start the copy.

## A variable stayed in the text. Why?

Check, in this order:

1. The value was empty. An empty value leaves the variable in place.
2. The spelling or the case differs: `{{project}}` is not `{{Project}}`.
3. Part of the variable has its own formatting, for example bold on one word.
   The variable has to be plain text in one piece.
4. The variable is in the space description. Variables are replaced in page
   titles, folder titles and page text only.

The report also lists pages that could not be updated, under **Pages not updated**.

## Some links still go to the source space. Why?

The app changes links that name the source space by its key. Links written as
full URLs and space keys in macro parameters stay as they are, so edit them by
hand in the new space.

## The report says “Space created, but some items were not copied”

The report shows what is missing: counts that do not match, or the sections
**Items that cannot be copied**, **Pages not updated**, **Page trees with errors**
and **Space roles not copied**. A single whiteboard is enough for this message.

## The copy stopped. What now?

The screen shows the reason. The new space stays as it was when the copy stopped:
the app does not delete it. If you do not need it, delete it in Confluence.

## The screen says the copy has not reported progress for 5 minutes

The buttons **Open space** and **Create another space** appear with this message.
The app waits up to 30 minutes for each page tree. After that it marks the tree
with `COPY_TIMED_OUT` in the report and goes on to the next one.

## Why was the home page named “… Home”?

Page titles in a space are unique. If a page of the source space already has the
title of the new space, the home page gets `<space name> Home`.

## Does a template keep its own copy of the pages?

No. A template stores the source space key and the settings. Each new space is
copied from the source space as it is at that moment. If the source space is
deleted, the copy stops with `Source space … was not found.`

## Does the app change the source space?

No. The app writes only to the new space.

## Who appears as the creator of the new pages?

The person who started the copy. We confirmed this on 7 November 2026 for a user
without administrator rights: that user was the creator of the space and of all
23 pages.

## What happens when the license is inactive?

The app shows a banner and closes creating spaces and changing templates. Viewing
and deleting templates still work, and a copy that has already started finishes.

## What happens if I uninstall the app?

Templates and copy jobs are removed. Spaces created by the app are ordinary
Confluence spaces, and the app has no code that removes them.

---

[← Documentation home](index.html) · [Privacy Policy →](privacy.html)

{% endraw %}
