
# ChatBridge

**ChatBridge** is an innovative communication platform that seamlessly bridges language barriers via WhatsApp. By leveraging advanced AI-driven translation models, ChatBridge translates messages in real-time, enabling fluid, natural conversations between people who speak different languages.

## Explore ChatBridge

🚀 **[Visit the ChatBridge GitHub Pages site](https://ironhack-datascientist.github.io/ChatBridge/)** to explore interactive visualizations, watch the introduction video, and dive deeper into how ChatBridge operates. The site provides a comprehensive view of the project's architecture, performance analysis, and more.

## Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Project Architecture](#project-architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Usage](#usage)
  - [How to Use ChatBridge](#how-to-use-chatbridge)
  - [Examples](#examples)
- [Performance Analysis](#performance-analysis)
  - [Translation Model Comparison](#translation-model-comparison)
  - [BLEU Score Analysis](#bleu-score-analysis)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## About the Project

In a globally connected world, language differences should no longer pose a barrier to effective communication. **ChatBridge** addresses this challenge by offering a real-time translation service via WhatsApp. Whether you're a business owner dealing with international clients or an individual connecting with friends abroad, ChatBridge ensures your messages are understood, regardless of the language.

ChatBridge integrates with Twilio and uses AI-powered translation models to translate messages as they are sent and received, maintaining the context and tone of the conversation.

## Features

- **Real-Time Translation:** Messages are translated instantly, providing smooth, uninterrupted conversations across languages.
- **Automatic Language Detection:** Detects the language of incoming messages without manual input.
- **Bidirectional Support:** Translates both incoming and outgoing messages for seamless dialogue.
- **Dynamic Target Management:** Easily assign target numbers for your translations via simple WhatsApp commands.
- **Advanced AI Models:** Uses Hugging Face and Gemini models to ensure high-quality translations.

## Project Architecture

ChatBridge is built on a robust architecture that ensures reliable and accurate message translation:

1. **Twilio Integration**: Handles the receipt and sending of WhatsApp messages.
2. **Language Detection API**: Automatically identifies the language of incoming messages.
3. **Translation Models**: Utilizes AI models (Hugging Face and Gemini) for translating messages.
4. **Backend Framework**: Implemented using Python and Flask for efficient request handling and processing.
5. **CSV Handler**: Manages language preferences and ISO codes for different WhatsApp numbers.

## Getting Started

To get a local copy up and running, follow these steps.

### Prerequisites

Ensure you have the following installed:

- Python 3.7+
- Flask
- Twilio API credentials
- Hugging Face and Gemini API access

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/IronHack-DataScientist/ChatBridge.git
    cd ChatBridge
    ```

2. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add your Twilio and API credentials, along with any other necessary environment variables.

### Running the Application

Start the Flask server:

```bash
flask run
```

The application will start, and you can begin sending messages to your Twilio number to see translations in action.

## Usage

### How to Use ChatBridge

1. **Start a Conversation**: Send a message to the Twilio number associated with ChatBridge. The message will be translated into the recipient's language and forwarded.
2. **Assign a Target Number**: Use the format `to:<target_number>` to direct your translated messages to a specific WhatsApp number.
3. **End a Session**: Use the command `exit` to clear the current target and end the session.

### Examples

- **Customer (English):** "Hello, I would like to know more about your services."
- **ChatBridge (Translation to Spanish):** "Hola, me gustaría saber más sobre sus servicios."
- **Business Owner (Spanish):** "Claro, ¿cómo puedo ayudarte?"
- **ChatBridge (Translation to English):** "Sure, how can I help you?"

## Performance Analysis

### Translation Model Comparison

ChatBridge employs both Hugging Face and Gemini translation models. We've conducted detailed performance analysis to compare these models in terms of speed and accuracy.

- **[Implementation of Hugging Face Models](https://github.com/IronHack-DataScientist/ChatBridge/blob/main/modules/translation/hf_translation.py)**
- **[Testing of Hugging Face Models](https://github.com/IronHack-DataScientist/ChatBridge/blob/main/modules/translation/hf_translation.py)**
- **[Translation Model Comparison](https://ironhack-datascientist.github.io/ChatBridge/#comparison-by-model):** A comprehensive comparison of how quickly each model translates different text types across various languages.
- **[Evaluation of Model Performance](https://github.com/IronHack-DataScientist/ChatBridge/blob/main/Jupyter%20Notebooks/Translation%20Performance%20Evaluation.ipynb)**

### BLEU Score Analysis

The BLEU score is a key metric used to evaluate the quality of translations. Our analysis includes:

- **[Visualizing Model Performance](https://github.com/IronHack-DataScientist/ChatBridge/blob/main/Jupyter%20Notebooks/Translation%20Performance%20Visualization.ipynb)**
- **BLEU Score Distribution**: Histograms and box plots that show the BLEU score distribution across different text types and languages.
- **Correlation Analysis**: A scatter plot examining the correlation between translation times and BLEU scores, offering insights into the trade-offs between speed and quality.

## Contributing

We welcome contributions from the community! If you have a feature request, bug report, or would like to contribute code, please follow these steps:

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

Please make sure to update tests as appropriate and adhere to the project's coding guidelines.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

For inquiries or support, please reach out to:

- **Your Name**
- **Email:** youremail@example.com
- **LinkedIn:** [Your LinkedIn Profile](https://www.linkedin.com/in/yourprofile)
- **GitHub:** [Your GitHub Profile](https://github.com/yourusername)

---

This project is actively maintained and continually improving. We appreciate your feedback and contributions to make ChatBridge even better!
