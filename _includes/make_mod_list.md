{% for mod in include.list %}
## {{ mod.name }}
{% include mod_template.md
  name             = mod.name
  developer        = mod.developer
  screenshot       = mod.screenshot
  description      = mod.description
  links            = mod.links
  depends          = mod.depends
  depends_optional = mod.depends_optional
%}
{% endfor %}
