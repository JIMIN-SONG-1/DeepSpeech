Speech Processing and Synthesis Project
This repository contains implementations of speech recognition and synthesis models using PyTorch. It includes two Automatic Speech Recognition (ASR) models (Listen, Attend and Spell and DeepSpeech2) and a Text-to-Speech (TTS) inference pipeline using Tacotron 2 with WaveGlow.

Table of Contents
Overview
Files
Requirements
Installation
Usage
Listen, Attend and Spell
DeepSpeech2
Tacotron 2 Inference
Dataset
References
Contributing
License
Overview
This project demonstrates:

Automatic Speech Recognition (ASR): Two models, Listen, Attend and Spell (LAS) and DeepSpeech2, are implemented to transcribe audio into text using the LibriSpeech dataset.
Text-to-Speech (TTS): A Tacotron 2 model with WaveGlow is used to synthesize audio from text, including mel-spectrogram generation and denoising.
The code is written in Python using PyTorch and is designed to run on GPU-enabled environments for efficient training and inference.

Files
Listen Attend Spell.ipynb: Implements the LAS model for ASR, featuring an encoder-decoder architecture with attention mechanisms.
DeepSpeech.ipynb: Implements the DeepSpeech2 model for ASR, using convolutional and recurrent layers with CTC loss.
inference.ipynb: Demonstrates TTS using a pre-trained Tacotron 2 model to generate mel-spectrograms and synthesize audio with WaveGlow.
Requirements
Python 3.6 or higher
PyTorch 2.7.1+cu118 or compatible
torchaudio
librosa
numpy
matplotlib
IPython
soundfile (for audio backend)
Additional dependencies for Tacotron 2 inference (see inference.ipynb)
Installation
Clone the repository:
bash

Comprimi

Testo a capo

Esegui

Copia
git clone https://github.com/your-username/speech-processing-synthesis.git
cd speech-processing-synthesis
Create a virtual environment and activate it:
bash

Comprimi

Testo a capo

Esegui

Copia
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install the required packages:
bash

Comprimi

Testo a capo

Esegui

Copia
pip install torch==2.7.1+cu118 torchaudio librosa numpy matplotlib ipython soundfile
For Tacotron 2, additional dependencies may be required. Refer to inference.ipynb for specifics.
Ensure CUDA is installed if using a GPU (check with torch.cuda.is_available()).
Usage
Listen, Attend and Spell
Open Listen Attend Spell.ipynb in Jupyter Notebook.
Ensure the LibriSpeech dataset (train-clean-100 and test-clean) is downloaded or available in the specified directory.
Run the notebook cells to preprocess audio, train the LAS model, and evaluate performance using Word Error Rate (WER) and Character Error Rate (CER).
DeepSpeech2
Open DeepSpeech.ipynb in Jupyter Notebook.
Download the LibriSpeech dataset as above.
Run the notebook to train the DeepSpeech2 model and evaluate it. The model uses a custom dataset loader (LibriSpeechDataset) to handle FLAC files via librosa.
Training progress and evaluation metrics (CER, WER) are printed during execution.
Tacotron 2 Inference
Open inference.ipynb in Jupyter Notebook.
Update checkpoint_path (Tacotron 2 model) and waveglow_path (WaveGlow model) to point to your pre-trained model files.
Modify the text variable to the desired input text for synthesis.
Run the notebook to generate mel-spectrograms, alignment plots, and audio output. The synthesized audio is denoised using the Denoiser class.
Dataset
The ASR models use the LibriSpeech dataset (train-clean-100 for training, test-clean for testing). The dataset is automatically downloaded via torchaudio.datasets.LIBRISPEECH if not already present in the ./data directory.

For Tacotron 2, pre-trained models are required, and no specific dataset is needed for inference.

References
Digital Signal Processing Lecture: GitHub
Python for Signal Processing: GitHub
Audio for Deep Learning: Link
Audio Preprocessing Practice: GitHub
Musical Applications of Machine Learning: Link
Awesome Audio Study Materials for Korean: GitHub
Contributing
Contributions are welcome! Please:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes and commit (git commit -m "Add feature").
Push to the branch (git push origin feature-branch).
Open a Pull Request.
License
This project is licensed under the MIT License. See the LICENSE file for details.