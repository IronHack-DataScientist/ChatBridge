---
layout: default
title: Welcome to ChatBridge
---

# ChatBridge

**ChatBridge** is an innovative communication platform designed to break down language barriers via WhatsApp. Our service acts as a real-time linguistic bridge, ensuring that conversations flow naturally and effortlessly across different languages. By leveraging advanced AI translation models, ChatBridge enables seamless and fluid communication between users around the world.

## Watch the Introduction Video

<div class="responsive-iframe-container">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/pIi9RA-OGJ8?start=9" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### Why ChatBridge?

In a globalized world, language should not be a barrier to effective communication. ChatBridge eliminates this obstacle by providing a seamless, real-time translation service directly through WhatsApp. Whether you're a business owner interacting with international clients or simply conversing with friends in different countries, ChatBridge ensures that your messages are translated accurately and quickly, allowing for meaningful interactions without misunderstandings.

### Key Features:
- **Real-Time Automatic Translation:** Instantly translates incoming and outgoing messages using state-of-the-art AI models like Hugging Face, with Gemini as a reliable backup.
- **Automatic Language Detection:** Effortlessly detects the language of incoming messages, ensuring smooth communication without the need for manual selection.
- **Bidirectional Support:** Allows for two-way translations, making conversations between people who speak different languages feel as natural as if they shared the same tongue.

## Project Architecture

### How It Works:
1. **Twilio Integration**: ChatBridge utilizes a Twilio number linked to your WhatsApp account to handle incoming and outgoing messages. This integration ensures that all communication is seamless and uninterrupted.
2. **Language Detection**: Our system automatically detects the language of incoming messages using an advanced language detection API, ensuring that every message is understood in the correct context.
3. **AI-Driven Translation Service**: Messages are translated using Hugging Face's powerful translation models, with Gemini as a backup to guarantee the highest possible translation quality.
4. **Dynamic Target Management**:
    - Business owners can dynamically assign target numbers by sending a simple WhatsApp command (e.g., `to:<target_number>`). This flexibility allows for easy management of multiple conversations.
    - The corresponding language and ISO code for each target number are retrieved and stored, optimizing future translations.

5. **Owner Message Handling**:
    - Messages starting with `to:` update the target recipient and language settings.
    - Regular text messages are translated and forwarded to the assigned target number.
    - Sending "exit" clears the current session, resetting all target information and ending the conversation.

6. **Responsive Replies**: The system ensures that replies from the recipient are translated back into the sender's language and sent through the Twilio number, maintaining the flow of conversation.

### Technical Foundation:
- **Twilio**: The backbone for handling WhatsApp messaging, Twilio ensures reliable delivery and receipt of messages across different networks.
- **Hugging Face & Gemini**: These AI models are at the heart of ChatBridge, delivering translations that are not only accurate but also contextually appropriate.
- **Python and Flask**: Our backend is built using Python and Flask, providing a robust framework for managing the workflow from language detection to message translation and delivery.
- **CSV Handler**: We utilize a custom CSV handler to manage language preferences and ISO codes, ensuring that our system is both scalable and easy to maintain.

## How to Use ChatBridge

1. **Start a Conversation**: Send a message to the Twilio number associated with ChatBridge. The system will detect the language and translate the message before forwarding it.
2. **Assign a Target Number**: As a business owner, assign a recipient for your translated messages by sending a command in the format `to:<target_number>`. This flexibility allows you to manage who receives your messages on the fly.
3. **Automatic Translation**: Once the target number is set, any message you send will be translated into the target language and delivered seamlessly.
4. **End a Session**: If you need to pause the translation service, simply send "exit" from your WhatsApp account to clear the session.

### Example in Action:
- **Scenario**: A Spanish-speaking business owner receives an inquiry in English.
    - **Customer (English)**: "Hello, I would like to know more about your services."
    - **ChatBridge**: Detects English, translates the message to Spanish, and forwards: "Hola, me gustaría saber más sobre sus servicios."
    - **Business Owner (Spanish)**: "Claro, ¿cómo puedo ayudarte?"
    - **ChatBridge**: Translates the response back to English and sends: "Sure, how can I help you?"

## Global Language Coverage (Tableau Visualizations)

### Understanding Global Language Distribution:
Explore how languages are distributed globally and the potential reach of ChatBridge with these interactive Tableau visualizations.

### People Around the World

This interactive map provides a comprehensive view of the primary languages spoken in different countries. Hover over a country to see detailed language statistics, including the number of speakers and the language's global significance.

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

### Languages by Countries

This bubble chart offers a clear visualization of how languages are spread across different countries. Each bubble's size reflects the number of countries where a language is spoken as the primary language, helping to understand the global impact of each language.

<div class="responsive-iframe-container">
    <div class='tableauPlaceholder' id='viz1724258619999' style='position: relative'>
        <noscript>
            <a href='#'><img alt='Languages by Countries' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;La&#47;Languagesarroundtheworld&#47;LanguagesbyCountries&#47;1_rss.png' style='border: none' /></a>
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

### Languages by People

This bubble chart visualizes the distribution of languages based on the number of speakers worldwide. It highlights the global reach of each language by comparing the total number of native and foreign speakers. Larger bubbles represent languages with more speakers, emphasizing their widespread influence.

<div class="responsive-iframe-container">
    <div class='tableauPlaceholder' id='viz1724258683205' style='position: relative'>
        <noscript>
            <a href='#'><img alt='Languages by People' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;La&#47;Languagesarroundtheworld&#47;LanguagesbyPeople&#47;1_rss.png' style='border: none' /></a>
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

# Performance Comparison by Translation Model

## Translation Times by Model

This bar chart compares the translation times between two AI models—Hugging Face (HF) and Gemini—demonstrating their efficiency in real-time text translation. The chart visualizes which model processes translations faster, providing valuable insights into performance under different conditions.

<div class="responsive-iframe-container">
    <iframe src="Resources/comparison_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Translation Times by Target Language and Model

This bar chart breaks down translation times by target language, comparing how quickly Hugging Face and Gemini models translate text into various languages. This analysis helps identify which model is more efficient for specific language pairs.

<div class="responsive-iframe-container">
    <iframe src="Resources/translation_times_by_target_language.html" width="100%" height="600px"></iframe>
</div>

## Translation Times by Text Type and Model

Here, we compare translation times based on the type of text—whether it’s a word, sentence, or paragraph. This bar chart illustrates how each model handles different levels of text complexity, providing insights into their strengths and weaknesses.

<div class="responsive-iframe-container">
    <iframe src="Resources/translation_times_by_text_type.html" width="100%" height="600px"></iframe>
</div>

## Heatmap of Translation Times by Source and Target Language

This heatmap provides a detailed view of translation times across various language pairs, broken down by the source and target languages. By comparing Hugging Face and Gemini, you can see how each model performs with different language combinations.

<div class="responsive-iframe-container">
    <iframe src="Resources/heatmap_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Distribution of Translation Times by Text Type and Model

A box plot is used to display the distribution of translation times across different text types, offering a clear picture of how each model (Hugging Face and Gemini) handles various translation challenges. This visualization helps identify which model is more consistent and reliable across different scenarios.

<div class="responsive-iframe-container">
    <iframe src="Resources/boxplot_translation_times.html" width="100%" height="600px"></iframe>
</div>

## Correlation Between HF and Gemini Translation Times by Language Pair

This scatter plot examines the correlation between the translation times of the Hugging Face and Gemini models for various language pairs. It highlights any patterns or discrepancies, revealing how different language complexities impact translation time.

<div class="responsive-iframe-container">
    <iframe src="Resources/scatter_translation_correlation.html" width="100%" height="600px"></iframe>
</div>

# BLEU Score Analysis for Translation Quality

BLEU (Bilingual Evaluation Understudy) scores are a widely accepted metric for evaluating the quality of machine translations. This analysis compares the BLEU scores of translations produced by Hugging Face against those by Gemini, using the latter as the reference.

## BLEU Score Calculation

1. **Calculation Process**: The BLEU score is calculated by comparing the Hugging Face translations against the reference translations produced by Gemini. We utilize the `sentence_bleu` function, which compares the word sequences in both translations.
2. **Applying the Function**: A custom function is applied across our dataset to compute BLEU scores for each translation, offering a quantitative measure of translation accuracy.
3. **Output**: The BLEU scores provide an immediate insight into which model produces translations that are closer to the reference.

## Distribution and Comparison of BLEU Scores

### Histogram of BLEU Scores

This histogram visualizes the distribution of BLEU scores, allowing us to see how closely the Hugging Face translations match those of Gemini across all translation pairs. The analysis helps identify the range and consistency of translation quality.

<div class="responsive-iframe-container">
    <iframe src="Resources/histogram_bleu_scores.html" width="100%" height="600px"></iframe>
</div>

### Box Plot of BLEU Scores by Text Type

This box plot compares BLEU scores across different text types, revealing how each model performs when translating words, sentences, and paragraphs. This analysis highlights which text types are more challenging for the models.

<div class="responsive-iframe-container">
    <iframe src="Resources/boxplot_bleu_scores.html" width="100%" height="600px"></iframe>
</div>

## BLEU Score Distribution by Source Language

### Histogram of BLEU Scores by Source Language

This histogram breaks down the distribution of BLEU scores by source language, offering insights into how translation quality varies depending on the language of origin.

<div class="responsive-iframe-container">
    <iframe src="Resources/histogram_bleu_scores_by_source_language.html" width="100%" height="600px"></iframe>
</div>

### Box Plot of BLEU Scores by Text Type and Source Language

This box plot further explores the BLEU scores, comparing them across different text types and source languages. The visualization helps pinpoint which combinations of language and text type pose the greatest challenges for translation models.

<div class="responsive-iframe-container">
    <iframe src="Resources/boxplot_bleu_scores_by_text_type_and_source_language.html" width="100%" height="600px"></iframe>
</div>

## Heatmap of Average BLEU Scores by Language Pair

This heatmap provides a visual representation of the average BLEU scores for each source-target language pair. It quickly identifies which language pairs yield the highest and lowest translation quality, offering a clear view of the models' strengths and weaknesses.

<div class="responsive-iframe-container">
    <iframe src="Resources/heatmap_average_bleu_score_by_language_pair.html" width="100%" height="600px"></iframe>
</div>

## Contributions and Future Improvements

ChatBridge is an evolving project, and we welcome contributions to enhance its capabilities. If you have ideas for new features, language support, or model improvements, feel free to collaborate with us.

### Future Improvements:
- Expanding support to include more languages.
- Enhancing language detection accuracy.
- Allowing users to customize translation models to better fit their needs.
