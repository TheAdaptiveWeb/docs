---
description: >-
  This guide will walk you through creating your first adapter for the Adaptive
  Web using awcli
---

# Getting Started with Adapter Development

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

In your workspace, you should now see an `index.ts` or `index.js` \(depending on wether you selected a TypeScript or JavaScript install\). In this guide, we will use TypeScript code snippets however the process is the same for JavaScript. Open this file in an IDE of your choice.

The generated script should look something like this:

{% tabs %}
{% tab title="TypeScript \(index.ts\)" %}
```typescript
import { AdapterContext } from 'adaptiveweb'; 
declare const aw: AdapterContext;

/* ... */

console.log('Hello, Adaptive Web!');
```
{% endtab %}

{% tab title="JavaScript \(index.js\)" %}
```javascript
/* ... */

console.log('Hello, Adaptive Web!');
```
{% endtab %}
{% endtabs %}

You can start writing your adapter code here. Adapters are injected directly into target web pages, so you should write your adapters assuming you have access to the window \(for example you call methods such as `document.findElementsByTagName`\). 

## Running your adapter

awcli features a watcher which lets you watches for changes to your adapter and rebuilds it as you make changes. It can then be tested on Chrome or Firefox using the developer mode built into the platform.

First, ensure you have developer mode enabled by visiting the [configuration site](https://adaptiveweb.io/configure) \(by visiting the link, or by clicking the Adaptive Web icon in the toolbar of your browser\), navigate to settings, and enable developer mode:

![](../.gitbook/assets/image%20%283%29.png)

{% hint style="info" %}
Automatic reload is enabled by default. This will reload the page when a change is detected in your adapter. You can disable this if you wish.
{% endhint %}

Then, return to your workspace, and run

```text
awcli watch
```

to start watching for changes.

