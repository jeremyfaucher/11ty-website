---
eleventyNavigation:
  parent: Filters
  key: inputPathToUrl Filter
  title: '<code>inputPathToUrl</code>'
  order: 4
  excerpt: 'Map a template’s input path to its output URL.'
---
# `inputPathToUrl` Universal Filter

{% addedin "3.0.0-alpha.5" %} Map a file’s location and to the template’s output URL. Very useful for robust hyperlinking allowing you to change your output URLs without breaking content links!

This filter is an alternative to the [InputPath To Url plugin](/docs/plugins/inputpath-to-url/), which provides an Eleventy transform that is less verbose but a bit slower.

The paths used here should be [relative to the input directory](/docs/config/#input-directory) though they _can_ be relative to the project root (the former is simpler and preferred).

<is-land on:visible import="/js/seven-minute-tabs.js">
<seven-minute-tabs>
  {% renderFile "./src/_includes/syntax-chooser-tablist.11ty.js", {id: "inputpathtourl"} %}
  <div id="inputpathtourl-liquid" role="tabpanel">

{% codetitle "Liquid", "Syntax" %}

{% raw %}
```liquid
<a href="{{ "index.md" | inputPathToUrl }}">Home</a>
```
{% endraw %}

  </div>
  <div id="inputpathtourl-njk" role="tabpanel">

{% codetitle "Nunjucks", "Syntax" %}

{% raw %}
```jinja2
<a href="{{ "index.md" | inputPathToUrl }}">Home</a>
```
{% endraw %}

  </div>
  <div id="inputpathtourl-js" role="tabpanel">

{% codetitle "JavaScript (CommonJS)", "Syntax" %}

{% raw %}
```js
module.exports = function(data) {
  return `<a href="${this.inputPathToUrl("index.md")}">Home</a>`;
}
```
{% endraw %}

  </div>
  <div id="inputpathtourl-jsesm" role="tabpanel">

{% codetitle "JavaScript (ESM)", "Syntax" %}

{% raw %}
```js
export default function(data) {
  return `<a href="${this.inputPathToUrl("index.md")}">Home</a>`;
}
```
{% endraw %}

  </div>
  <div id="inputpathtourl-hbs" role="tabpanel">

{% codetitle "Handlebars", "Syntax" %}

{% raw %}
```hbs
<a href="{{ inputPathToUrl "index.md" }}">Home</a>
```
{% endraw %}

  </div>
</seven-minute-tabs>
</is-land>

Renders as `<a href="/">Home</a>`.

---

[← Back to Filters documentation.](/docs/filters/)
