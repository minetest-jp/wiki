---
layout: default
title: 工業Mod
---
- 目次
{:toc}

{% for mod in site.data.mods_industry %}
  <h2>{{ mod.name }}</h2>
  {% include mod_template.html
    developer        = mod.developer
    screenshot       = mod.screenshot
    description      = mod.description
    links            = mod.links
    depends          = mod.depends
    depends_optional = mod.depends_optional
  %}
{% endfor %}
