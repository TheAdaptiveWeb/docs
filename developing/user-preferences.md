---
description: Specifying user-configurable preferences for your adapter.
---

# User Preferences

Users can specify preferences for your adapter through the configuration site. To achieve this, you must first create a schema which tells the Adaptive Web which preferences you want to allow your users to set, then you can access the preferences through the adapter context within your adapter code.

## Specifying a preference schema

To begin, open your awconfig.json:

{% code-tabs %}
{% code-tabs-item title="awconfig.json" %}
```javascript
{
    "id": "my-adapter",
    "name": "My Adapter",
    ...
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Add a new field called `preferenceSchema` which maps to an object

{% code-tabs %}
{% code-tabs-item title="awconfig.json" %}
```javascript
{
    "id": "my-adapter",
    "name": "My Adapter",
    ...
    "preferenceSchema": {
        
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Within the preference schema object you can start to define the preferences you would like to allow the user to change. Each preference has an associated key which maps to an object defining a user friendly name, description, default value, and [field type](user-preferences.md#supported-preference-types).

Below is an example of declaring a text field with key "myPreference" and default value of "Hello, World!":

{% code-tabs %}
{% code-tabs-item title="awconfig.json" %}
```javascript
{
    "id": "my-adapter",
    "name": "My Adapter",
    ...
    "preferenceSchema": {
        "myPreference": {
            "type": "text",
            "default": "Hello, World!",
            "friendlyName": "Message",
            "description": "Logged to the console by the adapter"
        }
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

If we now run our adapter on developer mode, we can see our preference has been added to the configuration site:

![](../.gitbook/assets/image%20%283%29.png)

## Accessing preferences from your adapter

Preferences can be accessed from the adapter by using the adapter context. A `getPreferences` method is exposed which returns the value of the preferences indexed by their key:

```javascript
aw.getPreferences().then(preferences => {
    /**
     * preferences = {
     *     myPreference: "Hello, World!"
     * }
     */
    console.log(preferences.myPreference);
});
```

## Supported preference types

Currently, the following list of preference types are supported by the platform:

| Type | Object type | Description |
| :--- | :--- | :--- |
| text | string | Text field with no additional validation |
| switch | boolean | A switch which can be set to on or off |

If you feel that the platform is missing a type, [please feel free to submit an issue](https://github.com/TheAdaptiveWeb/AdaptiveWeb.io/issues).

