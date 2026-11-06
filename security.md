---
title: Security Policy — Spacemold
---

# Security Policy

**App:** Spacemold

**Last updated:** 7 November 2026

[← Documentation home](index.html)

This policy describes how Spacemold ("the app"), developed and maintained by Vudia, protects your data and manages security risk. It complements our [Privacy Policy](privacy.html).

## 1. Architecture and Hosting

The app is built on **Atlassian Forge** and runs on Atlassian's infrastructure. It has no servers of its own and stores no data outside Atlassian. Its manifest declares no external permissions, so the Forge platform does not allow it to make outbound requests to other hosts, and its code contains none.

Infrastructure-level controls — transport encryption, platform patching, physical security — are provided by Atlassian under its shared responsibility model; see the [Atlassian Trust Center](https://www.atlassian.com/trust). We do not operate any infrastructure of our own.

## 2. Data We Handle

Full detail is in the [Privacy Policy](privacy.html); in summary:

- We store templates: their names, source space keys and copy settings.
- We store copy jobs for 30 days after their last change: the account ID of the person who started the copy, the name and key of the new space, the values of variables, titles of pages and folders, role assignments and the report.
- We never store passwords, email addresses, payment details, or the text of pages.
- The app writes only to the new space. It does not change the source space or any other existing space.

## 3. Authentication and Access Control

The app has no login or credential system of its own. Every request is authenticated by the Forge platform using the Confluence session of the signed-in person — we never collect, transmit, or store Atlassian usernames, passwords, or API tokens.

Access is checked on the server, for every request:

- saving and deleting a template require Confluence administrator rights;
- reading a copy job requires being the person who started it or a Confluence administrator;
- the template list, with template names and source space keys, is available to everyone who opens the app;
- the list of spaces is read with the signed-in person's own Confluence permissions.

All Confluence requests run as a person, never as the app itself. A copy takes longer than one request, so it runs in a Forge queue, where there is no session. For this the manifest declares `allowImpersonation`, and the queue function acts as the person who started the copy, using the account ID stored in the job. Confluence applies that person's permissions to every step: they need the right to create spaces, and pages closed to them do not reach the copy.

## 4. Declared Scopes

| Scope | Used for |
| --- | --- |
| `read:space:confluence`, `write:space:confluence` | Reading spaces, creating the new space |
| `read:page:confluence`, `write:page:confluence` | Reading pages, updating titles and text in the new space |
| `read:hierarchical-content:confluence` | Walking the page tree of the source space |
| `write:folder:confluence` | Creating folders in the new space |
| `read:attachment:confluence` | Counting attachments for the report |
| `read:space.permission:confluence`, `write:space.permission:confluence` | Reading role assignments of the source space, assigning them in the new space |
| `write:confluence-content`, `read:confluence-space.summary` | Copying pages and reading the status of the copy |
| `read:confluence-user` | Reading the person's display name and administrator rights |
| `storage:app` | Forge storage for templates and copy jobs |

All Confluence scopes except `read:confluence-user` are declared with `allowImpersonation`. No external or outbound permissions are declared.

## 5. Dependencies and Code

The source code is kept in a private GitHub repository. **Dependabot** alerts are enabled on it.

## 6. Vulnerability Management and Incident Response

Vulnerabilities reported to us — whether by Atlassian, a researcher, or a customer — are triaged and fixed within the timeframes of Atlassian's Marketplace policy for cloud apps.

If we identify or are notified of a security incident affecting the app:

1. We investigate and confirm scope and impact.
2. We notify Atlassian within 24 hours via a P1 support ticket, as required of Marketplace partners.
3. We contain and remediate the issue.
4. We notify affected customers directly if their data was affected.
5. We review the incident afterward and adjust our practices if needed.

To report a suspected vulnerability or security incident, email **security@vudia.site**. For general support, use **info@vudia.site**; security reports are prioritized ahead of general support requests.

## 7. Business Continuity

The app has no infrastructure of its own, so its availability depends on Atlassian Forge. There is no customer data outside Forge storage and your Confluence site, both operated by Atlassian.

## 8. Third-Party Risk

The only third party in our data flow is **Atlassian**, which hosts and operates Forge, Forge storage and Confluence. We do not use any other subprocessor, analytics service, or external API.

## 9. Compliance

We do not hold independent security certifications at this time; as a Forge app we rely on the infrastructure controls of Atlassian's platform.

## 10. Policy Review

This policy is reviewed at least annually, and whenever we make a material change to the app's architecture, data handling, or team.

## Contact

- **Security reports / vulnerability disclosure:** security@vudia.site
- **General support:** info@vudia.site — see [Support](support.html)
- **Privacy questions:** see our [Privacy Policy](privacy.html)

---

[← Privacy Policy](privacy.html) · [Documentation home](index.html) · [Support →](support.html)
