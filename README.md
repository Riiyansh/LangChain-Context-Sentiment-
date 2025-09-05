# Project Prototype – Audio Transcription, Summarization & Sentiment Analysis

This repository contains the prototype developed during the internship.  
The main work is inside the Jupyter Notebook (`project_prototype.ipynb`) file.  

---

## 📥 Downloading the Notebook

1. Click on the notebook file (`project_prototype.ipynb`) in this repository.  
2. On the top-right corner of the file preview, click **Download raw file**.  
   - Alternatively, clone the repository using:  
     ```bash
     git clone <repo-link>
     cd <repo-name>
     ```
   - The notebook will be available inside the cloned folder.  

---

## ▶️ Running the Notebook

You can run the notebook in **Google Colab** or **Jupyter Notebook**.

### Option 1: Run on Google Colab  
1. Open [Google Colab](https://colab.research.google.com/).  
2. Click on **File > Upload Notebook**.  
3. Select the downloaded `.ipynb` file.  
4. Run the cells in sequence.  

### Option 2: Run Locally (Jupyter Notebook)  
1. Make sure you have Python installed (≥3.8).  
2. Install Jupyter Notebook if not already installed:  
   ```bash
   pip install notebook
Navigate to the project folder and start Jupyter:

bash
Copy code
jupyter notebook
Open the .ipynb file and run all cells.

⚙️ Dependencies
The notebook installs most libraries automatically. Key packages include:

transformers (Whisper, BART summarizer)

datasets (support for NLP datasets)

librosa (audio loading & preprocessing)

pydub (MP3 → WAV conversion)

langchain (prompt handling, extensibility)

nltk (sentiment analysis with VADER)

🔍 How the Model Works
This prototype processes an audio file (MP3/WAV) and extracts insights in three stages:

Upload & Preprocessing

Uploads an .mp3 file.

Converts it to .wav format if needed.

Resamples to 16kHz for Whisper compatibility.

Transcription (Whisper)

Uses openai/whisper-small model from Hugging Face.

Converts raw speech into text (transcript).

Summarization (BART)

Uses facebook/bart-large-cnn.

Summarizes the transcript into a concise version.

Sentiment Analysis (VADER)

Applies NLTK’s VADER Sentiment Analyzer.

Produces polarity scores:

pos (positive sentiment)

neu (neutral sentiment)

neg (negative sentiment)

compound (overall sentiment score).

📊 Example Flow
Upload an MP3 call recording.

Transcription Output

css
Copy code
"Hello, thank you for calling. I’d like to know more about your services..."
Summary Output

arduino
Copy code
"The caller is asking about available services and requesting more details."
Sentiment Analysis Output

bash
Copy code
{'neg': 0.0, 'neu': 0.65, 'pos': 0.35, 'compound': 0.70}
🚀 Future Enhancements
Swap the Whisper model with larger versions (medium, large-v2) for better accuracy.

Replace the summarizer with paid LLMs (OpenAI GPT, Gemini, Claude) via LangChain.

Extend to multi-speaker diarization (who spoke what).

Add topic classification and emotion detection on top of sentiment analysis.

