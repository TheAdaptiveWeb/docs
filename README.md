---
description: An introduction to the Adaptive Web platform.
---

# Welcome to the Adaptive Web

The Adaptive Web is a platform for developing user-configurable _adapters_ which dynamically alter webpages to increase accessibility. The platform allows these adapters to run across browsers and devices with the same codebase.

![The Adaptive Web configuration site](.gitbook/assets/image%20%2812%29.png)

Adapters are add-ons which are injected into webpages to detect and rectify accessibility problems with the page. Adapters are provided with a set of tools that are implemented by _wrappers_ which bind the actions to platform-specific code. A common interface is provided to end-users to allow them to specify settings for each adapter.

## Motivation

The Adaptive Web was created to address a common problem in web accessibility; while a number of standards exist to try and ensure that pages are accessible, universal adoption remains an issue. By placing the burden of ensuring adoption on developers, we end up in a situation where - particularly developers with low budgets or time constraints - accessibility is seen as optional.

Due to this lack of attention, common errors occur which results in inaccessible sites. Many tools already exist to detect these errors \(some even suggesting code fixes\), but there is a lack of tooling around fixing these errors on end-user browsers.

Further, by providing such a platform we open the door to innovation that can only be provided in a decentralised manor such as automated audio description of videos, or client-side alt-tag generation.

