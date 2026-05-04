---
title: TMK Group — Privacy Policies
description: Privacy policies for the apps published by TMK Group.
permalink: /
---

# TMK Group privacy policies

Each TMK Group app has its own privacy policy describing the data it
handles. All apps share the same general principles: no selling, no
sharing, no advertising profile, on-device first, and minimum data
possible.

## Apps

<ul class="app-list">
{% assign apps = site.pages | where_exp: "p", "p.app_name" | sort: "order" %}
{% for app in apps %}
  <li>
    <a href="{{ app.url | relative_url }}">{{ app.app_name }}</a>
    <span class="desc">
      {%- if app.app_subtitle -%}{{ app.app_subtitle }} · {% endif -%}
      {{ app.data_collected | default: "See policy for data details." }}
    </span>
  </li>
{% endfor %}
</ul>

## General

For the principles that apply across every TMK Group app, see the
"TMK Group — General Privacy Statement" section embedded at the
bottom of each app-specific page above.

## Contact

[dev@tmkgroup.vn](mailto:dev@tmkgroup.vn)
