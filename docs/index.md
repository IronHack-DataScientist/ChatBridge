---
layout: default
title: Welcome to ChatBridge
---

# ChatBridge

**ChatBridge** is a text translation service via WhatsApp that acts as a linguistic bridge between people who speak different languages. By using a Twilio number, messages received in one language are automatically translated into the recipient's language. Responses are also translated back into the sender's original language, ensuring seamless communication.

## Watch the Introduction Video

<div class="responsive-iframe-container">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/pIi9RA-OGJ8?start=9" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


### Key Features:
- **Real-Time Automatic Translation:** Translates incoming and outgoing messages using translation models such as Hugging Face, with Gemini as a backup.
- **Automatic Language Detection:** The service automatically detects the language of incoming messages.
- **Bidirectional Support:** Messages are translated in both directions, allowing for smooth conversation between two people who speak different languages.

## Project Architecture

### Workflow:
1. **Twilio Integration**: Incoming messages are received through a Twilio number associated with your WhatsApp account.
2. **Language Detection**: The language of the incoming message is automatically detected using the translation API.
3. **Translation Service**: Messages are translated using Hugging Face as the primary translation service, with Gemini as a backup option if necessary.
4. **Assigning Target Numbers and Languages**: 
    - The service allows the business owner to dynamically assign a target number by sending a command like `to:<target_number>` via WhatsApp.
    - The language and ISO code associated with that target number are retrieved and stored for use in subsequent translations.
5. **Handling Messages from the Business Owner**:
    - If the message from the business owner starts with `to:`, the service updates the target recipient and language settings.
    - If the message is a normal text message, it gets translated and forwarded to the currently assigned target number.
    - If the message is "exit", the current session is ended, and all target information is cleared.
6. **Response Handling**: Replies from the recipient are translated back into the sender's language and relayed through the Twilio number.

### Technical Details:
- **Twilio**: Used to manage sending and receiving WhatsApp messages. The integration handles both incoming and outgoing message flows.
- **Hugging Face & Gemini**: These are the translation models utilized to ensure high-quality translations. Hugging Face is the primary model, while Gemini serves as a backup.
- **Python and Flask**: The backend is implemented using Python and Flask, managing the workflow from language detection to message translation and delivery.
- **CSV Handler**: A custom CSV handler is used to store and retrieve language preferences and ISO codes associated with different WhatsApp numbers.

## How to Use ChatBridge

1. **Start a Conversation**: Send a message to the Twilio number associated with the service. The service will detect the language and translate the message before forwarding it.
2. **Assign a Target Number**: As a business owner, you can set the recipient of your translated messages by sending a WhatsApp message with the format `to:<target_number>`. This command assigns a new recipient for your outgoing messages.
3. **Automatic Translation**: After setting the target number, any message you send will be automatically translated into the target language and sent to the designated number.
4. **End a Session**: If you wish to stop the translation service temporarily, send "exit" from your WhatsApp account. This will clear the current session.

### Example:
- **Scenario**: A Spanish-speaking business owner receives a message in English and wants to reply.
    - **Customer (English)**: "Hello, I would like to know more about your services."
    - **ChatBridge**: Detects English, translates the message to Spanish, and sends: "Hola, me gustaría saber más sobre sus servicios."
    - **Business Owner (Spanish)**: "Claro, ¿cómo puedo ayudarte?"
    - **ChatBridge**: Translates the message back to English and sends: "Sure, how can I help you?"


## People Around the World (Tableau)

This interactive map provides a visualization of the main languages spoken in different countries around the world. Each country is colored based on the primary language spoken, and when you hover over a specific country, a tooltip appears with detailed information about the languages and the speakers.

### Information Displayed:
- **Country:** The name of the country.
- **Habitants:** The total population of the country.
- **First Language:** The primary language spoken in the country.
- **1st Speakers:** The number of people who speak the primary language as their mother tongue.
- **Second Language:** An additional language spoken in the country, if applicable.
- **2nd Speakers:** The number of people who speak the second language.
- **People around the world who speak [Primary Language]:** Information about the total number of people who speak that language worldwide, divided into native speakers and foreign speakers.

This map is a powerful tool for understanding the global distribution of languages and how they relate to the population of each country. It also provides insight into languages that have significant influence both within and outside their countries of origin.

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

## Languages by Countries

This bubble chart visualizes the distribution of languages across different countries. Each bubble represents a language, and the size of the bubble corresponds to the number of countries where the language is spoken as the primary language. Larger bubbles indicate languages that are widely spoken across many countries, while smaller bubbles represent languages spoken in fewer countries.

### Information Displayed:
- **Bubble Size:** Represents the number of countries where the language is spoken as the first language.
- **Bubble Label:** Indicates the language name (e.g., English, Spanish, French).
- **Hover Tooltip:** When hovering over a bubble, additional information is displayed:
  - **First Language:** The language represented by the bubble.
  - **Countries that speak:** The total number of countries where this language is spoken as the primary language.

<div class="responsive-iframe-container">
    <div class='tableauPlaceholder' id='viz1724258619999' style='position: relative'>
        <noscript>
            <a href='#'>
                <img alt='Languages by Countries' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;La&#47;Languagesarroundtheworld&#47;LanguagesbyCountries&#47;1_rss.png' style='border: none' />
            </a>
        </noscript>
        <object class='tableauViz' style='display:none;'>
            <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
            <param name='embed_code_version' value='3' />
            <param name='site_root' value='' />
            <param name='name' value='Languagesarroundtheworld&#47;LanguagesbyCountries' />
            <param name='tabs' value='no' />
            <param name='toolbar' value='yes' />
            <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;La&#47;Languagesarroundtheworld&#47;LanguagesbyCountries&#47;1.png' />
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
        var divElement = document.getElementById('viz1724258619999');
        var vizElement = divElement.getElementsByTagName('object')[0];
        vizElement.style.width='100%';
        vizElement.style.height=(divElement.offsetWidth*0.75)+'px';
        var scriptElement = document.createElement('script');
        scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
        vizElement.parentNode.insertBefore(scriptElement, vizElement);
    </script>
</div>

## Languages by People

This bubble chart visualizes the distribution of languages based on the number of speakers worldwide. Each bubble represents a language, and the size of the bubble corresponds to the total number of people who speak that language, including both native and foreign speakers. Larger bubbles indicate languages with a higher number of speakers, while smaller bubbles represent languages with fewer speakers.

### Information Displayed:
- **Bubble Size:** Represents the total number of speakers (native and foreign) of the language.
- **Bubble Label:** Indicates the language name (e.g., Mandarin Chinese, English, Hindi).
- **Hover Tooltip:** When hovering over a bubble, additional information is displayed:
  - **Language:** The language represented by the bubble.
  - **Native by Language:** The number of people who speak the language as their mother tongue.
  - **Foreign Speakers:** The number of people who speak the language as a second or foreign language.

<div class="responsive-iframe-container">
    <div class='tableauPlaceholder' id='viz1724258683205' style='position: relative'>
        <noscript>
            <a href='#'>
                <img alt='Languages by People' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;La&#47;Languagesarroundtheworld&#47;LanguagesbyPeople&#47;1_rss.png' style='border: none' />
            </a>
        </noscript>
        <object class='tableauViz' style='display:none;'>
            <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
            <param name='embed_code_version' value='3' />
            <param name='site_root' value='' />
            <param name='name' value='Languagesarroundtheworld&#47;LanguagesbyPeople' />
            <param name='tabs' value='no' />
            <param name='toolbar' value='yes' />
            <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;La&#47;Languagesarroundtheworld&#47;LanguagesbyPeople&#47;1.png' />
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
        var divElement = document.getElementById('viz1724258683205');
        var vizElement = divElement.getElementsByTagName('object')[0];
        vizElement.style.width='100%';
        vizElement.style.height=(divElement.offsetWidth*0.75)+'px';
        var scriptElement = document.createElement('script');
        scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
        vizElement.parentNode.insertBefore(scriptElement, vizElement);
    </script>
</div>

# Comparison by Model

## Comparison of Translation Times by Model

This bar chart compares the translation times between two different translation models, "HF" and "Gemini." The data is melted to align both models on a single axis, showing the translation time (in seconds) for each model. The bars are grouped by model, allowing for a clear comparison of performance in terms of speed.

- **HF Model**: Represents the translation times taken by the HF translation system.
- **Gemini Model**: Represents the translation times taken by the Gemini translation system.

This visualization helps to quickly assess which model performs translations faster under the given conditions.

<div class="responsive-iframe-container">
    <iframe src="Resources/comparison_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Translation Times by Target Language and Model

This bar chart illustrates the translation times (in seconds) for two different translation models, "HF" and "Gemini," across various target languages. The chart groups the bars by target language and distinguishes between the models using color.

- **Target Language**: The language into which the text is being translated.
- **HF Model**: Represents the translation times for the HF translation system.
- **Gemini Model**: Represents the translation times for the Gemini translation system.

This visualization allows for a comparative analysis of how each model performs in translating into different target languages, highlighting variations in speed across languages and models.

<div class="responsive-iframe-container">
    <iframe src="Resources/translation_times_by_target_language.html" width="100%" height="600px"></iframe>
</div>

## Translation Times by Text Type and Model

This bar chart displays the translation times (in seconds) for two different translation models, "HF" and "Gemini," categorized by text type. The chart groups the bars by text type, with color distinguishing the two models.

- **Text Type**: The category of text being translated, such as word, sentence, or paragraph.
- **HF Model**: Represents the translation times for the HF translation system.
- **Gemini Model**: Represents the translation times for the Gemini translation system.

This visualization provides insight into how each model performs across different types of text, allowing for a comparative analysis of translation speed based on the complexity or length of the text.

<div class="responsive-iframe-container">
    <iframe src="Resources/translation_times_by_text_type.html" width="100%" height="600px"></iframe>
</div>

## Heatmap of Translation Times by Source and Target Language

This heatmap visualizes the translation times (in seconds) for different source and target language pairs across two translation models, "Hugging Face" and "Gemini." The data is displayed in two facets, one for each model, allowing a side-by-side comparison of how each model performs across various language pairs.

- **Source Language**: The original language of the text before translation.
- **Target Language**: The language into which the text is translated.
- **Translation Time (s)**: The time taken by each model to perform the translation, represented by color intensity on the heatmap.

The heatmap provides a clear overview of how translation time varies depending on the source and target language combination, as well as differences in performance between the two models.

<div class="responsive-iframe-container">
    <iframe src="Resources/heatmap_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Translation Times by Source and Target Language for Each Model

This bar chart illustrates the translation times (in seconds) for various source and target language pairs across two different translation models: "HF" and "Gemini." The data is displayed in two separate facets, one for each model, allowing for a direct comparison of performance across languages within each model.

- **Source Language**: The original language of the text before translation.
- **Target Language**: The language into which the text is translated.
- **Translation Time (s)**: The time taken by each model to perform the translation.

The bars are grouped by target language within each source language category, providing a visual comparison of translation times between different language pairs for both the HF and Gemini models. This chart highlights the variations in translation speed depending on the language combination and the translation model used.

<div class="responsive-iframe-container">
    <iframe src="Resources/translation_times_by_language_and_model.html" width="100%" height="600px"></iframe>
</div>

## Distribution of Translation Times by Text Type and Model

A box plot can effectively display the distribution of translation times across different text types for the two translation models, "HF" and "Gemini." This plot will highlight the median, quartiles, and potential outliers in the translation times, providing insights into the consistency and variability of each model's performance. By comparing these distributions, you can assess which model is more consistent across different text types and identify any significant differences in translation time.

<div class="responsive-iframe-container">
    <iframe src="Resources/boxplot_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Correlation Between HF and Gemini Translation Times by Language Pair

A scatter plot can be used to explore the correlation between translation times for the HF and Gemini models across different language pairs. This type of plot will help identify if there are specific source-target language pairs that consistently require more time, potentially revealing linguistic complexities or inefficiencies in the models. The scatter plot can be color-coded by the source language and use different symbols for the target languages to enhance interpretability.

<div class="responsive-iframe-container">
    <iframe src="Resources/scatter_translation_correlation.html" width="100%" height="600px"></iframe>
</div>

# BLEU Score Calculation for Translation Performance

This snippet of code calculates the BLEU (Bilingual Evaluation Understudy) score, a common metric for evaluating the quality of machine-translated text. In this case, the BLEU score is used to compare the translations produced by the "HF" (Hugging Face) model against the "Gemini" model, which is treated as the reference translation.

## Explanation

1. **BLEU Score Calculation**:
   - The BLEU score is calculated by comparing the candidate translation (produced by the HF model) against a reference translation (produced by the Gemini model).
   - The `sentence_bleu` function from the `nltk.translate.bleu_score` module is used, which requires splitting the text into words (tokens) and then comparing these tokens between the candidate and reference translations.
   - A smoothing function (`SmoothingFunction().method1`) is applied to handle cases where the candidate translation may not have any n-grams in common with the reference.

2. **Function Definition**:
   - `calculate_bleu(row)`: This function takes a row from the dataframe, splits the "Gemini Translated Text" and "HF Translated Text" into word tokens, and calculates the BLEU score between them.

3. **Applying the Function**:
   - The `apply` method is used to apply the `calculate_bleu` function to each row of the dataframe, creating a new column `BLEU Score` that stores the result.

4. **Visualization**:
   - The script prints the `HF Translated Text`, `Gemini Translated Text`, and the corresponding `BLEU Score` for each row in the dataframe, allowing for a quick comparison of translation quality between the two models.

## Distribution and Comparison of BLEU Scores

This code snippet generates two key visualizations to analyze the BLEU scores calculated from the comparison of translations between the "HF" (Hugging Face) and "Gemini" models.

### 1. Histogram of BLEU Scores
- **Purpose**: The histogram visualizes the distribution of BLEU scores across all translation pairs.
- **Details**: 
  - The BLEU scores are binned into 20 intervals (`nbins=20`), providing a clear view of how the scores are spread out.
  - The histogram helps to identify the range of BLEU scores, showing whether most translations are close to the reference or if there's significant variability in the quality of translations.

### 2. Box Plot of BLEU Scores by Text Type
- **Purpose**: The box plot compares the distribution of BLEU scores across different text types (e.g., word, sentence, paragraph).
- **Details**:
  - The x-axis represents different text types, while the y-axis shows the corresponding BLEU scores.
  - The box plot displays the median, quartiles, and any outliers in the BLEU scores for each text type, allowing for a comparison of translation quality between text types.
  - This visualization helps identify whether certain types of text are consistently harder to translate accurately for the HF model compared to the Gemini model.

  <div class="responsive-iframe-container">
    <iframe src="Resources/histogram_bleu_scores.html" width="100%" height="600px"></iframe>
</div>

<div class="responsive-iframe-container">
    <iframe src="Resources/boxplot_bleu_scores.html" width="100%" height="600px"></iframe>
</div>

## BLEU Score Distribution by Source Language

This code snippet calculates the BLEU score for each translation in the dataset, comparing the "HF" (Hugging Face) model translations against the "Gemini" model as the reference. The BLEU scores are then visualized in a histogram, with the distribution separated by source language.

### BLEU Score Calculation
- **Purpose**: The function `calculate_bleu` computes the BLEU score for each translation pair, using the "Gemini" translation as the reference and the "HF" translation as the candidate.
- **Details**: The BLEU score provides a numerical measure of how closely the HF translations match the Gemini translations, with smoothing applied to handle rare or zero n-gram overlaps.

### Histogram of BLEU Scores by Source Language
- **Purpose**: The histogram visualizes the distribution of BLEU scores across different source languages.
- **Details**:
  - The BLEU scores are binned into 20 intervals (`nbins=20`), and the bars are color-coded by source language.
  - This visualization highlights how translation quality, as measured by BLEU score, varies depending on the source language.
  - The histogram allows for an easy comparison of BLEU score distributions across different languages, identifying which languages may present more challenges in achieving high-quality translations.

<div class="responsive-iframe-container">
    <iframe src="Resources/histogram_bleu_scores_by_source_language.html" width="100%" height="600px"></iframe>
</div>

## Comparison of BLEU Scores by Text Type and Source Language

This code snippet generates a box plot to compare the BLEU scores across different text types and source languages. The plot provides insights into how translation quality, as measured by BLEU score, varies depending on the type of text and the language of the original text.

### Box Plot of BLEU Scores
- **Purpose**: The box plot visually compares the distribution of BLEU scores for different text types (e.g., word, sentence, paragraph) and separates these comparisons by source language.
- **Details**:
  - The x-axis represents the text type, while the y-axis shows the corresponding BLEU scores.
  - The boxes are color-coded by source language, allowing for a clear comparison of translation quality across languages for each text type.
  - The box plot displays the median, quartiles, and any outliers in BLEU scores, highlighting variations in translation accuracy based on both the text type and the language of origin.
  - This visualization helps identify which combinations of text type and source language result in more accurate or less accurate translations according to the BLEU metric.

<div class="responsive-iframe-container">
    <iframe src="Resources/boxplot_bleu_scores_by_text_type_and_source_language.html" width="100%" height="600px"></iframe>
</div>

## Heatmap of Average BLEU Scores by Language Pair

This code snippet creates a heatmap to visualize the average BLEU scores for each source-target language pair. The heatmap provides a clear, comparative view of translation quality across different language pairs.

### Grouping and Averaging BLEU Scores
- **Purpose**: The data is first grouped by source and target languages, and the mean BLEU score is calculated for each language pair.
- **Details**:
  - The `groupby` function is used to aggregate BLEU scores by language pairs, providing the average BLEU score for each combination of source and target language.
  - This aggregation allows for a high-level comparison of translation accuracy across different language pairs.

### Heatmap of Average BLEU Scores
- **Purpose**: The heatmap visually represents the average BLEU scores across all language pairs, making it easy to identify which pairs yield higher or lower translation quality.
- **Details**:
  - The x-axis represents the source language, and the y-axis represents the target language.
  - The color intensity in each cell corresponds to the average BLEU score for that particular language pair.
  - This visualization helps in identifying which language pairs are more challenging to translate accurately and which pairs yield better translation performance, as indicated by higher BLEU scores.

<div class="responsive-iframe-container">
    <iframe src="Resources/heatmap_average_bleu_score_by_language_pair.html" width="100%" height="600px"></iframe>
</div>

## Contributions and Future Improvements

We welcome contributions and suggestions to improve ChatBridge. If you have ideas on how we can enhance the service or if you'd like to collaborate, feel free to open an issue or submit a pull request.

### Future Improvements:
- Support for more languages.
- Improved accuracy in language detection.
- User customization of translation models.