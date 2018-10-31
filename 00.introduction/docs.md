---
title: Introduction
taxonomy:
    category: docs
---

This add-on is designed to help facilitate basic a/b tests in your ExpressionEngine templates. It works closely with the Bloqs fieldtype, but can also work as a standalone add-on if you do not use Bloqs. Experiments only determines which template code to output during ExpressionEngine's template parsing routine, which means it running server side. You will need to use additional tools like Google Optimize, Visual Website Optimizer, Optimizely, or some other client side service to configure and capture the results of your test. These client side tools offer what is usually referred to as a redirect based a/b test, meaning you must include a small snippet of JavaScript in the head of your page, and the JavaScript determines if it should stay on the current page (usually the original) or redirect to the another page (your variant). Each URL needs to be unique, which is why this add-on is expecting the ``?v=N`` GET parameter in the URL, where N can be blank, 1, or 2.

For additional information on client side and server side a/b testing see the following resources:

* https://www.optimizely.com/resources/client-vs-server-side-testing-infographic/
* https://speakerdeck.com/boldminded/b-testing
