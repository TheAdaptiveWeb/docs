---
description: >-
  This guide will walk you through creating your first adapter for the Adaptive
  Web using awcli.
---

# Getting Started with Adapter Development

## Prerequisites

To follow this guide, you need [node.js](https://nodejs.org) and [npm](https://npmjs.com) installed. You should also have installed [the Adaptive Web browser extension for Chrome or Firefox](../installing-the-adaptive-web.md).

Adapters are built with TypeScript or JavaScript. For guides about writing in these languages, see the following resources:

* TypeScript in 5 minutes - [https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)
* JavaScript \| MDN - [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

## Installing awcli

_awcli_ is the official command line tooling for the Adaptive Web. While it is possible to create adapters without awcli, it provides tools to get up and running right away. It also features integration with the Adaptive Web for Web Extensions, which allows you to debug your adapters in real-time through Chrome or Firefox.

Install the tools with npm:

```text
npm install -g awcli
```

## Creating an adapter workspace

Once the tools have been installed, you can create an adapter workspace:

```bash
mkdir MyAdapter
cd MyAdapter
awcli init
```

Running `awcli init` will run you through the required setup. Here you will define a name, description, version, and type of install you would like. Adapters can be written in TypeScript or JavaScript. Select your preference and complete the rest of the initiation \(if your unsure of what value to put for certain fields, you can leave them as the default for now\).

Once you have entered the information, the tools will install the necessary dependencies.

## Writing your adapter

In your workspace, you should now see an `index.ts` or `index.js` \(depending on wether you selected a TypeScript or JavaScript install\). Open this file in an IDE of your choice.

The generated script should look something like this:

{% tabs %}
{% tab title="TypeScript" %}
{% code-tabs %}
{% code-tabs-item title="index.ts" %}
```typescript
import { AdapterContext } from 'adaptiveweb'; 
declare const aw: AdapterContext;

/* ... */

console.log('Hello, Adaptive Web!');
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="JavaScript" %}
{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
/* ... */

console.log('Hello, Adaptive Web!');
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

You can start writing your adapter code here. Adapters are injected directly into target web pages, so you should write your adapters assuming you have access to the window \(for example you call methods such as `document.findElementsByTagName`\). 

## Running your adapter

awcli features a watcher which lets you watches for changes to your adapter and rebuilds it as you make changes. It can then be tested on Chrome or Firefox using the developer mode built into the platform.

First, ensure you have developer mode enabled by visiting the [configuration site](https://adaptiveweb.io/configure) \(by visiting the link, or by clicking the Adaptive Web icon in the toolbar of your browser\), navigate to settings, and enable developer mode:

![](../.gitbook/assets/image%20%2814%29.png)

{% hint style="info" %}
Automatic reload is enabled by default. This will reload the page when a change is detected in your adapter. You can disable this if you wish.
{% endhint %}

Then, return to your workspace, and run

```text
awcli watch
```

to start watching for changes.

## Using the adapter context

Adapters have access to the _adapter context_, an object which exposes methods that are implemented by browser-specific wrappers.

By using the adapter context, you can access:

* [User-specified preferences for your adapter](user-preferences.md),
* [Adaptive Web flavoured UI elements](ui-elements.md),
* [The web request API](making-web-requests.md)

## Building a production-ready version of your adapter

To build a production-ready version of your adapter, you can run

```text
awcli build
```

This will output your compiled and optimised adapter to a JSON file under your workspace directory at `dist/[YOUR_ADAPTER_ID].json`.

## Publishing your adapter

Once you have finished development, you can publish your adapter with

```text
awcli publish
```

This will redirect you to login with GitHub if this is your first time publishing. Once you have logged in, awcli will create a draft pull request \(PR\) for you.

Provide a description for your adapter, and any additional information you want to add. When you are ready, submit the PR and await our final decision.

We code review every adapter to ensure security and quality, so please keep in mind that this process can take some time.

