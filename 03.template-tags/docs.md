---
title: Template Tags
taxonomy:
    category: docs
---

## Content Tag Pair

The ``content`` tag pair is designed to work with any type of content you can output in your ExpressionEngine templates. If the current page is part of an a/b test, this tag will determine which tag pair of content to output to the page. By default, if ``?v=2`` is in your URL, all the content within the ``{original}{/original}`` tag pair will be removed from the output to the page, and content within the ``{variant}{/variant}`` tag pair will be displayed. If ``?v=1`` or the ``?v`` GET parameter is not defined, then the content within the ``{original}{/original}`` tag pair will be displayed.

```
{exp:experiments:content}
   {original}
       Original Content #1
   {/original}

   Always Shown

   {original}
       Original Content #2
   {/original}

   {variant}
       Variant Content #1
   {/variant}
{/exp:experiments:content}
```

### Parameters

``choose="[1|2]"``

Choose which variation to show, either the original (1) or variant (2). This will override any value defined as a GET parameter, or randomly choosen by the plugin.

``prefix="var:"``

The ``{original}{/original}`` and ``{variant}{/variant}`` tag pairs can be prefixed with the defined parameter value. For example ``{var:original}{/var:original}``

## Bloqs Tag Pair

Add an Experiments atom to your block and make it a block variable by prefixing the short name with `block_var` [See Bloqs documentation](https://eebloqs.com/documentation/nesting). It can be named anything, for example, `block_var_experiment` or `block_var_test`. This field is designed to work with Bloqs' nestable mode, but will also work with nesting turned off. If you add it to a parent block all child blocks will be hidden or removed based
on the value chosen in the field, and which version of the experiment is being displayed to the end user.

The only updates you need to make to your template  is to wrap the main Bloqs field tag pair with the experiments plugin tag. That's it. Bloqs and the Experiment field will handle the rest as long as the GET parameter ``?v=N`` is present.

```
{exp:channel:entries channel="pages" entry_id="{segment_2}"}
      {exp:experiments:bloqs}
          {bloqs_field}
              ... blocks ...
          {/bloqs_field}
      {/exp:experiments:bloqs}
 {/exp:channel:entries}
 ```


