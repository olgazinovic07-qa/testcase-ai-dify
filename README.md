# TestCase AI 📝⚙️

An advanced QA Automation assistant built on top of the **Dify** platform. This tool takes functional requirements described in plain text, processes them through a multi-stage AI pipeline, and generates a structured, ready-to-use set of positive and negative test cases in valid **JSON format**.

---

## 🚀 Live Demo & Links

You can test and interact with the **TestCase AI** agent using the official interfaces below:

* **[Telegram Bot](https://t.me/OlgaZin_bot)** — Quick and conversational testing interface on Telegram.
* **[Web Application (Dify)](https://udify.app/chat/R2g9rKJQBQpYds6D)** — Full standalone web-chat interface powered directly by Dify.

---

## 🛠️ Multi-Stage Pipeline Architecture

Instead of a single raw prompt, this project utilizes a structured **Workflow** to guarantee high-quality test generation and strict JSON compliance:

1. **Check_Completeness (Codestral 25.01):** Validates the user input to ensure it contains enough logical data to generate valuable tests. If not, it gracefully routes the flow to an error handler.
2. **Masking_Data:** Cleans and processes the input data for the testing environment.
3. **QA_Generator:** Acts as a specialized QA Automation Engineer, drafting core positive and negative test scenarios in raw text format.
4. **QA_Reviewer:** Acts as a Senior QA Lead, reviewing the drafted test cases for completeness, logical edge cases, and boundary values.
5. **JSON_Conversion:** Translates the polished test cases into strict JSON array structure without any conversational text or markdown code blocks.
6. **Save_as_file:** Bundles the generated JSON code into a standard downloadable `.json` file for the end user.

---

## 📥 How to Import This Project Into Your Dify Account

You can easily clone this exact workflow logic into your own workspace using the provided `.yml` files.

### Prerequisites
* A free or premium account at **[Dify.ai](https://dify.ai)**
* Access to LLM models (e.g., Mistral/Codestral API keys, OpenAI, or any alternative configured in your Dify workspace).

### Step-by-Step Installation:
1. Download the required configuration file from this repository:
   * `test_cases_chatflow.yml` — for the standalone **Web Chat** interface.
   * `test_cases_workflow.yml` — for the **Telegram Bot** backend integration.
2. Log into your **Dify Dashboard**.
3. Go to the **Studio** tab and click on **Create from Blank**.
4. In the setup modal, select **Import DSL file**.
5. **Crucial Step:** Choose the correct application type before uploading the file:
   * Choose **Chatflow** if you are importing the `test_cases_chatflow.yml` file.
   * Choose **Workflow** if you are importing the `test_cases_workflow.yml` file.
6. Upload your downloaded `.yml` file and click **Create**.
7. **Note on Safety & Models:** All private API keys have been completely stripped during export. Upon import, open your block settings and map the nodes (like `Check_Completeness` and `QA_Generator`) to your own active LLM providers (e.g., Codestral, OpenAI, etc.).
8. Click **Publish** in the top right corner. Your personal instance is live!

---

## 🤖 Connecting the Workflow to Telegram

To make your `Workflow` instance respond to users in Telegram, you need to connect the Dify API with a Telegram Bot token.

### 1. Create a Bot via BotFather
1. Open Telegram and search for **[@BotFather](https://t.me)**.
2. Send the `/newbot` command and follow the instructions to choose a name and username.
3. Copy the generated **HTTP API Token** (it looks like `123456789:ABCdefGhIJKlmNoPQRsTUVwxyZ`).


### 2. Link Telegram with Dify
1. In your Dify Dashboard, open your imported **Workflow** project.
2. Navigate to the **Monitoring** or **Publish** tab on the left menu.
3. Look for **Integrations / Telegram** (if supported by your self-hosted or cloud version).
4. Paste your HTTP API Token there and click **Save**.

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
