---
description: Adding Adaptive Web flavoured UI elements to web pages.
---

# UI Elements

The Adaptive Web provides a number of UI elements to use within your adapter outside the box. The advantage of using these UI helpers is twofold;

* Since the elements share the look and feel of the configuration site, users will be able to have a more seamless experience, and
* UI elements will be styled in accordance with the user selected theme.

{% hint style="info" %}
UI elements should be used sparingly, and only when user input is required, or for situations in which information is being displayed for users who use screen readers.
{% endhint %}

## Cards

Cards are containers which allow for content to be organised

![An example of a card, here used in the Video Audio Description adapter](../.gitbook/assets/image%20%286%29.png)

### When to use

{% hint style="success" %}
**DO:** 

* Use a card when displaying actions or information that are pertinent to the user based on the current context
{% endhint %}

{% hint style="danger" %}
**AVOID:** 

* Nesting multiple card elements; cards should be treated as standalone elements
* Blocking information
{% endhint %}

### Usage

{% tabs %}
{% tab title="TypeScript" %}
#### Initiating a card

Create a blank with no children:

```typescript
let card: AWCard = aw.ui.card();
```

Create a card with a number of children:

```typescript
let card: AWCard = aw.ui.card([ child1, child2, ... ]);
```

Create a card with additional CSS properties:

```typescript
let card: AWCard = aw.ui.card([], {
    /* CSS properties go here */
    display: 'flex',
    alignItems: 'center'
});
```

{% hint style="info" %}
Note that when setting CSS properties, if the property name contains a hyphen \(such as `align-items`\), the property must be referred to in lower camel case \(i.e. `alignItems`\)
{% endhint %}

#### Card methods

Once a card has been initiated, a number of methods can be called on it.

To add children, use the `appendChild` method. Children can be of type `AWElement` or `HTMLElement`:

```typescript
card.appendChild(child);
```

If you wish to hide the card from screen readers, you can use the `setSightedVisibility` method. Set to `false` if you wish to hide the card from the DOM, but maintain visibility for screen readers:

```typescript
card.setSightedVisibility(false);
```
{% endtab %}

{% tab title="JavaScript" %}
#### Initiating a card

Create a blank with no children:

```javascript
let card = aw.ui.card();
```

Create a card with a number of children:

```javascript
let card = aw.ui.card([ child1, child2, ... ]);
```

Create a card with additional CSS properties:

```typescript
let card = aw.ui.card([], {
    /* CSS properties go here */
    display: 'flex',
    alignItems: 'center'
});
```

{% hint style="info" %}
Note that when setting CSS properties, if the property name contains a hyphen \(such as `align-items`\), the property must be referred to in lower camel case \(i.e. `alignItems`\)
{% endhint %}

#### Additional methods

Once a card has been initiated, a number of methods can be called on it.

To add children, use the `appendChild` method. Children can be of type `AWElement` or `HTMLElement`:

```javascript
card.appendChild(child);
```

If you wish to hide the card from screen readers, you can use the `setSightedVisibility` method. Set to `false` if you wish to hide the card from the DOM, but maintain visibility for screen readers:

```javascript
card.setSightedVisibility(false);
```
{% endtab %}
{% endtabs %}

## Text

Text elements are used to display text to the user.

### Usage

{% tabs %}
{% tab title="TypeScript" %}
#### Initiating a text element

Create a text element with the string `Hello, World!`:

```typescript
let text: AWText = aw.ui.text('Hello, World!');
```

Create a text element with a given font size:

```typescript
let text: AWText = aw.ui.text('Hello, World!', 18);
```

Create a text element with additional CSS properties:

```typescript
let text: AWText = aw.ui.text('Hello, World!', undefined, {
    /* CSS properties go here */
    color: '#eee'
});
```

{% hint style="info" %}
Note that when setting CSS properties, if the property name contains a hyphen \(such as `align-items`\), the property must be referred to in lower camel case \(i.e. `alignItems`\)
{% endhint %}

#### Additional methods

Once a text element has been created, the text can be updated with the `setText` method.

```typescript
text.setText(child);
```
{% endtab %}

{% tab title="JavaScript" %}
#### Initiating a text element

Create a text element with the string `Hello, World!`:

```typescript
let text = aw.ui.text('Hello, World!');
```

Create a text element with a given font size:

```typescript
let text = aw.ui.text('Hello, World!', 18);
```

Create a text element with additional CSS properties:

```typescript
let text = aw.ui.text('Hello, World!', undefined, {
    /* CSS properties go here */
    color: '#eee'
});
```

{% hint style="info" %}
Note that when setting CSS properties, if the property name contains a hyphen \(such as `align-items`\), the property must be referred to in lower camel case \(i.e. `alignItems`\)
{% endhint %}

#### Additional methods

Once a text element has been created, the text can be updated with the `setText` method.

```typescript
text.setText(child);
```
{% endtab %}
{% endtabs %}

## Button

Buttons allow users to make actions directly from a target page.

![](../.gitbook/assets/image%20%287%29.png)

### Usage

{% tabs %}
{% tab title="TypeScript" %}
#### Initiating a button

Create a button with the string `Click Me!` and a simple onClick listener:

```typescript
let button: AWButton = aw.ui.button('Click Me!', () => {
    // Handle button click
    console.log('Button clicked');
});
```

Create a button with a different type, in this case `danger`:

```typescript
let button: AWButton = aw.ui.button('Click Me!', () => {
    // Handle button click
    console.log('Button clicked');
}, 'danger');
```

Create a button with additional CSS properties:

```typescript
let button: AWButton = aw.ui.button('Click Me!', () => {
    // Handle button click
    console.log('Button clicked');
}, undefined, {
    /* CSS properties go here */
    color: '#eee'
});
```

{% hint style="info" %}
Note that when setting CSS properties, if the property name contains a hyphen \(such as `align-items`\), the property must be referred to in lower camel case \(i.e. `alignItems`\)
{% endhint %}

#### Additional methods

Once a button has been created, the text can be updated with the `setText` method.

```typescript
button.setText(child);
```

The type of the button can be altered with the `setType` method:

```typescript
button.setType('danger');
```
{% endtab %}

{% tab title="JavaScript" %}
#### Initiating a button

Create a button with the string `Click Me!` and a simple onClick listener:

```typescript
let button = aw.ui.button('Click Me!', () => {
    // Handle button click
    console.log('Button clicked');
});
```

Create a button with a different type, in this case `danger`:

```typescript
let button = aw.ui.button('Click Me!', () => {
    // Handle button click
    console.log('Button clicked');
}, 'danger');
```

Create a button with additional CSS properties:

```typescript
let button = aw.ui.button('Click Me!', () => {
    // Handle button click
    console.log('Button clicked');
}, undefined, {
    /* CSS properties go here */
    color: '#eee'
});
```

{% hint style="info" %}
Note that when setting CSS properties, if the property name contains a hyphen \(such as `align-items`\), the property must be referred to in lower camel case \(i.e. `alignItems`\)
{% endhint %}

#### Additional methods

Once a button has been created, the text can be updated with the `setText` method.

```typescript
button.setText(child);
```

The type of the button can be altered with the `setType` method:

```typescript
button.setType('danger');
```
{% endtab %}
{% endtabs %}

## Other elements

You can still fall back on other element types by creating elements with the `document.createElement` method. If you think an element should be supported by the platform, please [please feel free to submit an issue](https://github.com/TheAdaptiveWeb/AdaptiveWeb.io/issues).

