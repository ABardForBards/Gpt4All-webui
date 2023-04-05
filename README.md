# Gpt4All Web UI

![GitHub license](https://img.shields.io/github/license/ParisNeo/Gpt4All-webui)

![GitHub issues](https://img.shields.io/github/issues/ParisNeo/Gpt4All-webui)

![GitHub stars](https://img.shields.io/github/stars/ParisNeo/Gpt4All-webui)

![GitHub forks](https://img.shields.io/github/forks/ParisNeo/Gpt4All-webui)

This is a Flask web application that provides a chat UI for interacting with the GPT4All chatbot.

## What is GPT4All

GPT4All is a language model built by Nomic-AI, a company specializing in natural language processing. The app uses Nomic-AI's library to communicate with the GPT4All model, which runs locally on the user's PC. For more details about this project, head on to their [github repository](https://github.com/nomic-ai/gpt4all). You can also reald their [Technical report](https://s3.amazonaws.com/static.nomic.ai/gpt4all/2023_GPT4All_Technical_Report.pdf) for more information about the training process, the batabase etc.

The app allows users to send messages to the chatbot and view its responses in real-time. Additionally, users can export the entire chat history in text or JSON format.

The model has just been released and it may evolve over time, this webui is meant for community to get easy and fully local access to a chatbot that may become better with time.

## Disclaimer

The model used by GPT4ALL has been fine-tuned using the LORA technique on LLAMA 7B weights (for now). It is important to note that the LLAMA weights are under commercial proprietary license, and therefore, this model cannot be used for commercial purposes. We do not provide the weights ourselves, but have built a UI wrapper on top of the Nomic library, which downloads the weights automatically upon running the program.

It is important to understand that we are not responsible for any misuse of this tool. Please use it responsibly and at your own risk. While we hope that Nomic will address this issue in the future by providing clean weights that can be used freely, for now, this model is intended for testing purposes only.

## UI screenshot

![image](https://user-images.githubusercontent.com/827993/229349273-221b6bfc-475e-4be3-8d98-fb8f0036df8e.png)

**Note for Windows users:** At the moment, Nomic-AI has not provided a wheel for Windows, so you will need to use the app with the Windows Subsystem for Linux (WSL). To install WSL, follow these steps:

Open the Windows Features settings (you can find this by searching for "Windows Features" in the Start menu).

Enable the "Windows Subsystem for Linux" feature.

Restart your computer when prompted.

Install a Linux distribution from the Microsoft Store (e.g., Ubuntu).

Open the Linux distribution and follow the prompts to create a new user account.

We apologize for any inconvenience this may cause. W

## Installation

To install the app, follow these steps:

1.  Clone the GitHub repository:

```
git clone https://github.com/higorvaz/Gpt4All-webui
```

1.  Navigate to the project directory:

```
cd Gpt4All-webui
```

1.  Run the appropriate installation script for your platform:

On Windows with WSL:

When Nomic add windows support you would be able to use this :

On Linux or macOS:

\- Install requirements  
python3.11 -m pip install -r requirements.txt 

![](https://user-images.githubusercontent.com/9384127/230159652-120e60f3-b737-434a-ac01-15819a0e7698.png)

\- Review the install script 🙏🏻

```
nano -lASimYsh install.sh
```

![](https://user-images.githubusercontent.com/9384127/229646387-9fea98c6-fb13-496b-b8eb-9db6fe241556.png)

\- Make it runnable

```
chmod +x install.sh
```

\- Run the install script

```
./install.sh
```

![](https://user-images.githubusercontent.com/9384127/229650379-e70a54b3-a8c0-44c6-a44f-26b96dfbcf4e.png)

\- Install nomic 

```
pip install nomic
```

![](https://user-images.githubusercontent.com/9384127/229660511-ea6ef97e-712a-4e59-81d4-b4162e796728.png)

![](https://user-images.githubusercontent.com/9384127/229660570-a960cfc3-4634-4354-868f-259ba9ffe888.png)

\- Install/updt venv 

```
sudo apt install python3.11-venv
```

![](https://user-images.githubusercontent.com/9384127/229801745-3c84e89e-c62c-460d-9e79-dafe5aa518d5.png)

\- ToDo

These scripts will create a Python virtual environment and install the required dependencies.

## Usage

To run the Flask server, execute the following command:

```bash
python app.py [--port PORT] [--host HOST] [--temp TEMP] [--n-predict N_PREDICT] [--top-k TOP_K] [--top-p TOP_P] [--repeat-penalty REPEAT_PENALTY] [--repeat-last-n REPEAT_LAST_N] [--ctx-size CTX_SIZE]
```

![](https://user-images.githubusercontent.com/9384127/229806717-1b260484-723f-4780-b69b-d19c7375a84e.png)

![](https://user-images.githubusercontent.com/9384127/229807131-623e9017-1536-473c-9e54-58d64f007991.png)

![](https://user-images.githubusercontent.com/9384127/229809099-3ef4d87f-18ce-4873-b43b-e6f9d7accb50.png)

![Magic Memes](https://www.memesmonkey.com/images/memesmonkey/77/771330e9f7a2a22e7b412187a657045c.jpeg)

😅

## Options

*   `--port`: the port on which to run the server (default: 9600)
*   `--host`: the host address on which to run the server (default: localhost)
*   `--temp`: the sampling temperature for the model (default: 0.1)
*   `--n-predict`: the number of tokens to predict at a time (default: 128)
*   `--top-k`: the number of top-k candidates to consider for sampling (default: 40)
*   `--top-p`: the cumulative probability threshold for top-p sampling (default: 0.90)
*   `--repeat-penalty`: the penalty to apply for repeated n-grams (default: 1.3)
*   `--repeat-last-n`: the number of tokens to use for detecting repeated n-grams (default: 64)
*   `--ctx-size`: the maximum context size to use for generating responses (default: 2048)

Note: All options are optional, and have default values.

Once the server is running, open your web browser and navigate to http://localhost:9600 (or http://your host name:your port number if you have selected different values for those) to access the chatbot UI. To use the app, open a web browser and navigate to this URL.

Make sure to adjust the default values and descriptions of the options to match your specific application.

## Contribute

This is an open-source project by the community for the community. Our chatbot is a UI wrapper for Nomic AI's model, which enables natural language processing and machine learning capabilities.

We welcome contributions from anyone who is interested in improving our chatbot. Whether you want to report a bug, suggest a feature, or submit a pull request, we encourage you to get involved and help us make our chatbot even better.

Before contributing, please take a moment to review our [code of conduct](./CODE_OF_CONDUCT.md). We expect all contributors to abide by this code of conduct, which outlines our expectations for respectful communication, collaborative development, and innovative contributions.

### Reporting Bugs

If you find a bug or other issue with our chatbot, please report it by [opening an issue](https://github.com/your-username/your-chatbot/issues/new). Be sure to provide as much detail as possible, including steps to reproduce the issue and any relevant error messages.

### Suggesting Features

If you have an idea for a new feature or improvement to our chatbot, we encourage you to [open an issue](https://github.com/your-username/your-chatbot/issues/new) to discuss it. We welcome feedback and ideas from the community and will consider all suggestions that align with our project goals.

### Contributing Code

If you want to contribute code to our chatbot, please follow these steps:

1.  Fork the repository and create a new branch for your changes.
2.  Make your changes and ensure that they follow our coding conventions.
3.  Test your changes to ensure that they work as expected.
4.  Submit a pull request with a clear description of your changes and the problem they solve.

We will review your pull request as soon as possible and provide feedback on any necessary changes. We appreciate your contributions and look forward to working with you!

Please note that all contributions are subject to review and approval by our project maintainers. We reserve the right to reject any contribution that does not align with our project goals or standards.

## Future Plans

Here are some of the future plans for this project:

**Enhanced control of chatbot parameters:** We plan to improve the user interface (UI) of the chatbot to allow users to control the parameters of the chatbot such as temperature and other variables. This will give users more control over the chatbot's responses, and allow for a more customized experience.

**Extension system for plugins:** We are also working on an extension system that will allow developers to create plugins for the chatbot. These plugins will be able to add new features and capabilities to the chatbot, and allow for greater customization of the chatbot's behavior.

**Enhanced UI with themes and skins:** Additionally, we plan to enhance the user interface of the chatbot to allow for themes and skins. This will allow users to personalize the appearance of the chatbot, and make it more visually appealing.

We are excited about these future plans for the project and look forward to implementing them in the near future. Stay tuned for updates!

## License

This project is licensed under the Apache 2.0 License. See the [LICENSE](https://github.com/ParisNeo/Gpt4All-webui/blob/main/LICENSE) file for details.

## Special thanks

Special thanks to [cclaar-byte](https://github.com/cclaar-byte) and [CybearWarfare](https://github.com/CybearWarfare) for enhancing the UI.

```
install.bat
```

```
./install.sh
```
