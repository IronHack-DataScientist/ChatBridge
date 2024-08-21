---
layout: default
title: Bienvenido a ChatBridge
---

# ChatBridge
Bienvenido a la página de ChatBridge. Aquí puedes explorar datos y visualizaciones interactivas.

## People Around the World (Tableau)
<div class="responsive-iframe-container">
    <div class='tableauPlaceholder' id='viz1724256313985' style='position: relative'>
        <noscript>
            <a href='#'><img alt='People Around the World' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;5X&#47;5XGHZWKPX&#47;1_rss.png' style='border: none' /></a>
        </noscript>
        <object class='tableauViz'  style='display:none;'>
            <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
            <param name='embed_code_version' value='3' />
            <param name='path' value='shared&#47;5XGHZWKPX' />
            <param name='toolbar' value='yes' />
            <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;5X&#47;5XGHZWKPX&#47;1.png' />
            <param name='animate_transition' value='yes' />
            <param name='display_static_image' value='yes' />
            <param name='display_spinner' value='yes' />
            <param name='display_overlay' value='yes' />
            <param name='display_count' value='yes' />
            <param name='language' value='es-ES' />
            <param name='filter' value='publish=yes' />
        </object>
    </div>
    <script type='text/javascript'>
        var divElement = document.getElementById('viz1724256313985');
        var vizElement = divElement.getElementsByTagName('object')[0];
        vizElement.style.width='100%';
        vizElement.style.height=(divElement.offsetWidth*0.75)+'px';
        var scriptElement = document.createElement('script');
        scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
        vizElement.parentNode.insertBefore(scriptElement, vizElement);
    </script>
</div>

## Comparison of Translation Times by Model

This bar chart compares the translation times between two different translation models, "HF" and "Gemini." The data is melted to align both models on a single axis, showing the translation time (in seconds) for each model. The bars are grouped by model, allowing for a clear comparison of performance in terms of speed.

- **HF Model**: Represents the translation times taken by the HF translation system.
- **Gemini Model**: Represents the translation times taken by the Gemini translation system.

This visualization helps to quickly assess which model performs translations faster under the given conditions.

<div class="responsive-iframe-container">
    <iframe src="Resources/comparison_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Dashboard Interactivo de Tableau
<div class="responsive-iframe-container">
    <iframe src="tableau_dashboard.html" width="100%" height="600px"></iframe>
</div>
