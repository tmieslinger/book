<!-- This file was created automatically -->
# HALO

```{admonition} How to plan a HALO flight
:class: info
For an introduction to the HALO flight planning, [click here](../plans/howto)
```

For an overview of all flight categories, [click here](flight_categories).

Flight-ID | Date | Takeoff | Landing | PI | Nickname | Categories
--- | --- | --- | --- | --- | --- | ---
{% for k, v in flights.items() -%}
{% set c1 = v["refs"]|join(", ") -%}
{% set c2 = v["takeoff"].strftime("%d %B %Y") -%}
{% set c3 = v["takeoff"].strftime("%X") -%}
{% set c4 = v["landing"].strftime("%X") -%}
{% set c5 = v["pi"] -%}
{% set c6 = v["nickname"] -%}
{{ k }} ({{ c1 }}) | {{ c2 }} | {{ c3 }} | {{ c4 }} | {{ c5 }} | {{ c6 }} | {% for cat in v["categories"] %}{flight-cat}`{{cat}}` {% endfor %}
{% endfor -%}
