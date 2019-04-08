---
description: This guide walks you through installing the Adaptive Web for your browser.
---

# Installing the Adaptive Web

{% hint style="info" %}
The Adaptive Web is currently only available as a developer preview.
{% endhint %}

Currently the Adaptive Web is available on the following platforms:

1. [Google Chrome](installing-the-adaptive-web.md#chrome),
2. [Mozilla Firefox](installing-the-adaptive-web.md#mozilla-firefox),
3. [Microsoft Edge](installing-the-adaptive-web.md#microsoft-edge),
4. Safari \(coming soon\)
5. iOS \(coming soon\)
6. Android \(coming soon\)

To suggest a new platform, or to help contribute to porting the Adaptive Web, [please submit an issue on GitHub](https://github.com/TheAdaptiveWeb/AdaptiveWeb.io/issues).

## Google Chrome

To install the Adaptive Web on Chrome, [visit the Google Web Store](https://chrome.google.com/webstore/detail/the-adaptive-web/ibmiojohcbhflaemkafgnafpagjkiadf).

![](.gitbook/assets/image%20%284%29.png)

Click the "Add to Chrome" button. You will be presented with a popup with the permissions we require. In order for us to be able to fix accessibility problems, we need to be able to read and make changes to web pages. No data from the page is sent to an external server or source of any kind, and we only use this permission to find and correct problems on the current page.

![](.gitbook/assets/image%20%2810%29.png)

Click "Add extension" when you are ready to proceed. You will then be presented with a success message telling you that the Adaptive Web has been added to Chrome.

![](.gitbook/assets/image%20%2820%29.png)

[Take a look at our "Configuring Adapters" guide to get started using The Adaptive Web](configuring-adapters.md).

## Mozilla Firefox

{% hint style="info" %}
Firefox support is currently only available as a debug add-on. Full support through the normal channels is coming soon.
{% endhint %}

Open Firefox, and navigate to `Tools -> Add-ons` from the top navigation bar:

![](.gitbook/assets/image%20%289%29.png)

You will be presented with a currently installed list of add-ons. Click the settings dropdown and select "Debug Add-ons" as shown below:

![](.gitbook/assets/image%20%2814%29.png)

![](.gitbook/assets/image%20%2817%29.png)

Enable add-on debugging by clicking the checkbox:

![](.gitbook/assets/image%20%2816%29.png)

Grab the latest release from GitHub at [https://github.com/TheAdaptiveWeb/AdaptiveWeb-WebExtensions/releases](https://github.com/TheAdaptiveWeb/AdaptiveWeb-WebExtensions/releases), and download "TheAdaptiveWeb.zip". Extract the zip to a location of your choice.

Now, go back to Firefox and select "Load Temporary Add-on". Navigate to where you extracted the zip, and open "manifest.json" with the file explorer.

The Adaptive Web is now installed. ​[Take a look at our "Configuring Adapters" guide to get started using The Adaptive Web](https://app.gitbook.com/@theadaptiveweb/s/adaptiveweb/~/edit/drafts/-LbxR30wGVNyg3uaboxS/configuring-adapters).

## Microsoft Edge

To install the Adaptive Web on Edge, [follow this guide](https://docs.microsoft.com/en-us/microsoft-edge/extensions/guides/adding-and-removing-extensions) and refer to the [Firefox instructions](installing-the-adaptive-web.md#mozilla-firefox).

## Safari

A wrapper for Safari is coming soon. [Track the progress of this here](https://github.com/TheAdaptiveWeb/AdaptiveWeb.io/issues/28).

