---
layout: default
title: Configuration
parent: Thales
nav_order: 1
---

Just the Docs has some specific configuration parameters that can be defined in your Jekyll site's _config.yml file.

View this site's [_config.yml](https://github.com/pmarsceill/just-the-docs/tree/master/_config.yml) file as an example.


## Site logo

```yaml
# Set a path/url to a logo that will be displayed instead of the title
logo: "/assets/images/just-the-docs.png"
```

## Search

```yaml
# Enable or disable the site search
# Supports true (default) or false
search_enabled: true

search:
  # Split pages into sections that can be searched individually
  # Supports 1 - 6, default: 2
  heading_level: 2
  # Maximum amount of previews per search result
  # Default: 3
  previews: 3
  # Maximum amount of words to display before a matched word in the preview
  # Default: 5
  preview_words_before: 5
  # Maximum amount of words to display after a matched word in the preview
  # Default: 10
  preview_words_after: 10
  # Set the search token separator
  # Default: /[\s\-/]+/
  # Example: enable support for hyphenated search words
  tokenizer_separator: /[\s/]+/
  # Display the relative url in search results
  # Supports true (default) or false
  rel_url: true
  # Enable or disable the search button that appears in the bottom right corner of every page
  # Supports true or false (default)
  button: false
```

## Color scheme

```yaml
# Color scheme supports "light" (default) and "dark"
color_scheme: dark
```
<button class="btn js-toggle-dark-mode">Preview dark color scheme</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'Preview dark color scheme';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'Return to the light side';
  }
});
</script>

# Customization


## Color schemes
{: .d-inline-block }

New
{: .label .label-green }

Just the Docs supports two color schemes: light (default), and dark.

To enable a color scheme, set the `color_scheme` parameter in your site's `_config.yml` file:

#### Example


```yaml
# Color scheme supports "light" (default) and "dark"
color_scheme: dark
```
<button class="btn js-toggle-dark-mode">Preview dark color scheme</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'Preview dark color scheme';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'Return to the light side';
  }
});
</script>

## Custom schemes

### Define a custom scheme

You can add custom schemes.
If you want to add a scheme named `foo` (can be any name) just add a file `_sass/color_schemes/foo.scss` (replace `foo` by your scheme name)
where you override theme variables to change colors, fonts, spacing, etc.

Available variables are listed in the [_variables.scss](https://github.com/pmarsceill/just-the-docs/tree/master/_sass/support/_variables.scss) file.

For example, to change the link color from the purple default to blue, include the following inside your scheme file:

#### Example


```scss
$link-color: $blue-000;
```

_Note:_ Editing the variables directly in `_sass/support/variables.scss` is not recommended and can cause other dependencies to fail.
Please use scheme files.

### Use a custom scheme

To use the custom color scheme, only set the `color_scheme` parameter in your site's `_config.yml` file:
```yaml
color_scheme: foo
```

### Switchable custom scheme

If you want to be able to change the scheme dynamically, for example via javascript, just add a file `assets/css/just-the-docs-foo.scss` (replace `foo` by your scheme name)
with the following content:`

{% raw %}
    ---
    ---
    {% include css/just-the-docs.scss.liquid color_scheme="foo" %}
{% endraw %}

This allows you to switch the scheme via the following javascript.

```js
jtd.setTheme('foo');
```

## Override and completely custom styles

For styles that aren't defined as variables, you may want to modify specific CSS classes.
Additionally, you may want to add completely custom CSS specific to your content.
To do this, put your styles in the file `_sass/custom/custom.scss`.
This will allow for all overrides to be kept in a single file, and for any upstream changes to still be applied.

For example, if you'd like to add your own styles for printing a page, you could add the following styles.

#### Example


```scss
// Print-only styles.
@media print {
  .side-bar, .page-header { display: none; }
  .main-content { max-width: auto; margin: 1em;}
}
```
