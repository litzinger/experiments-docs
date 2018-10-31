---
title: Experiments
taxonomy:
    category: docs
---

You can override the GET parameter name that Experiments uses to get the value of which variation to choose. By default it defaults to ``v``. Add the following array to your config.php file to override the default settings.

```
$config['experiments'] = [
    'queryParameterName' => 'v',
    'queryParameterValue' => null,
    'randomize' => true,
];
```