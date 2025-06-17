# Meeting Summarizer with Audio Transcription

This project uses a Jupyter notebook to transcribe meeting audio files and generate detailed meeting minutes, including a summary, discussion points, and action items, using state-of-the-art AI models. The interface is provided via Gradio, allowing users to input the path to an audio file stored in Google Drive and receive a text summary.

## ✨ Features

- **Audio Transcription:** Transcribes meeting audio into text using OpenAI's Whisper model.
- **Meeting Minutes Generation:** Utilizes Meta's Llama 3.1 model to process the transcription and generate a formatted markdown summary.
- **Detailed Summary:** The generated minutes include an overall summary, key discussion points, conclusions, and action items with assigned responsibilities.
- **Interactive Interface:** Employs Gradio to create a simple user interface where users can provide the audio file path and obtain the result.
- **Memory Efficiency:** Loads the large language model (LLM) with 4-bit quantization to optimize memory usage in GPU environments.

## 🤖 Models Used

- **Speech Recognition:** `openai/whisper-medium`
- **Language Generation:** `meta-llama/Meta-Llama-3.1-8B-Instruct`

## 🛠️ Technologies and Libraries

- Python
- PyTorch
- Transformers (Hugging Face)
- BitsAndBytes (for quantization)
- Gradio (for the user interface)
- Google Colab (execution environment)
- Google Drive (for file storage)

## 🚀 Setup and Installation

To run this project, it's recommended to use a Google Colab environment with a GPU accelerator.

### Prerequisites

- A Google account with access to Google Drive.
- A Hugging Face account with an access token.

### Clone the Repository

```bash
git clone https://github.com/novaisDiogo/summary_transcript_audio.git
````

### Add your Hugging Face Token

- In Google Colab, click on the key icon (**Secrets**) in the left menu.
- Create a new secret named `HF_TOKEN`.
- Paste your Hugging Face access token into the value field.

### Prepare the Audio File

- Upload your audio file (e.g., `.mp3`) to your Google Drive.  
  The source code expects it to be in a folder, for example: `/MyDrive/llms/`.  
  You can adjust the path as needed.

### Run the Notebook

- Open the `summary_transcript_audio.ipynb` file in Google Colab.
- Run the cells in order. The first cell will install all necessary dependencies.
- Subsequent cells will:
  - Mount your Google Drive
  - Authenticate with Hugging Face
  - Load the AI models

## ▶️ How to Use

- After executing all notebook cells, a Gradio interface will launch, and a public link (`share=True`) will be displayed at the end of the output.
- Open the link in your browser.
- In the **"Audio File Path:"** text box, enter the path to your audio file relative to your main Google Drive folder.  
  For example, if your file is in `MyDrive/my_meetings/audio.mp3`, you should enter: my_meetings/audio.mp3.
- Click the **"Summary"** button.
- Wait for processing. The model will first transcribe the audio and then generate the summary. The result will appear in the **"Result:"** text box.

