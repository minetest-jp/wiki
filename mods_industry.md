---
layout: default
title: 工業Mod
---
- 目次
{:toc}

{% for mod in site.data.mods_industry %}
## {{ mod.name }}
{% include mod_template.html
  developer        = mod.developer
  screenshot       = mod.screenshot
  description      = mod.description
  links            = mod.links
  depends          = mod.depends
  depends_optional = mod.depends_optional
%}
{% endfor %}
