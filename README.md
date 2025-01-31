DeepSeek AI - VS Code Extension
This VS Code extension integrates the DeepSeek AI model into your editor, allowing you to interact with the model directly from a webview panel. You can ask questions and get responses in real-time.

Prerequisites
Before using this extension, ensure you have the following installed:

Node.js: Required to run the extension and its dependencies.

Download and install Node.js from here.

VS Code: The extension is built for Visual Studio Code.

Download and install VS Code from here.

Ollama: The extension uses the Ollama library to interact with the DeepSeek AI model.

Install Ollama by following the instructions here.

DeepSeek Model: Ensure the deepseek-r1:latest model is installed on your Ollama server.

Run the following command to pull the model:

bash
Copy
ollama pull deepseek-r1:latest
Installation
Clone the Repository:
Clone this repository to your local machine:

bash
Copy
git clone https://github.com/your-username/deepseek-ai-vscode-extension.git
cd deepseek-ai-vscode-extension
Install Dependencies:
Install the required Node.js dependencies:

bash
Copy
npm install
Install the Extension in VS Code:

Open the project in VS Code.

Press F5 to compile and run the extension in a new VS Code window.

Usage
Start the Extension:

Open the Command Palette in VS Code (Ctrl+Shift+P or Cmd+Shift+P on macOS).

Search for and select DeepSeek AI: Start.

Interact with DeepSeek AI:

A webview panel will open in the editor.

Type your question in the text area and click "Ask" to get a response from the DeepSeek AI model.

Hello World Command:

Open the Command Palette.

Search for and select DeepSeek AI: Hello World.

A notification will appear with the message: "Hello World from Rasulov Tokhir!"

Configuration
Ollama Server
By default, the extension connects to the Ollama server at http://localhost:11434. If your Ollama server is running on a different host or port, update the Ollama initialization in the activate function:

typescript
Copy
const ollama = new Ollama({ host: "http://your-ollama-host:port" });
Model Selection
To use a different model, update the model property in the ollama.chat call:

typescript
Copy
const streamResponse = await ollama.chat({
  model: "your-model-name", // Replace with your desired model
  messages: [{ role: "user", content: userPrompt }],
  stream: true,
});
Troubleshooting
1. Model Not Found
If you encounter the error model "deepseek-r1:latest" not found, ensure the model is installed:

bash
Copy
ollama pull deepseek-r1:latest
2. Ollama Server Not Running
Ensure the Ollama server is running. Start it with:

bash
Copy
ollama serve
3. Extension Not Working
Check the VS Code Developer Tools (Help > Toggle Developer Tools) for any errors.

Ensure all dependencies are installed by running:

bash
Copy
npm install
Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Screenshots
Webview Panel
Webview Panel

Hello World Notification
Hello World Notification

Acknowledgments
Ollama for providing the AI model interface.

VS Code API for enabling extension development.

