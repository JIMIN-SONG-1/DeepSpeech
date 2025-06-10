음성 인식 및 합성 실험 🎙️



🔊 PyTorch로 구현한 최신 음성 인식(ASR)과 음성 합성(TTS) 모델을 체험하세요! 이 저장소는 DeepSpeech2, Listen, Attend and Spell (LAS), 그리고 Tacotron 2 with WaveGlow를 포함합니다. LibriSpeech 데이터셋으로 음성 처리의 세계를 탐험해 보세요! 🚀



📑 목차





✨ 프로젝트 소개



🛠️ 설치 가이드



🎮 실행 방법



📂 파일 안내



📚 참고 자료



📜 라이선스



✨ 프로젝트 소개

이 프로젝트는 음성 처리 기술의 핵심을 구현합니다:





🗣️ DeepSpeech2: CNN, 양방향 GRU, CTC 손실로 구성된 엔드투엔드 음성 인식 모델. LibriSpeech 데이터셋에서 학습.



👂 Listen, Attend and Spell (LAS): 어텐션 기반 인코더-디코더 모델로, LibriSpeech를 활용한 음성 인식.



🎵 Tacotron 2 with WaveGlow: 텍스트를 멜-스펙트로그램으로 변환하고 WaveGlow로 고품질 오디오를 합성하는 TTS 시스템.

PyTorch 기반으로, 오디오 전처리 파이프라인과 WER(단어 오류율), CER(문자 오류율) 평가 지표를 제공합니다. 음성 AI의 매력을 직접 경험해 보세요! 😎



🛠️ 설치 가이드

📋 필수 요구 사항





🐍 Python: 3.8 이상



💻 GPU: CUDA 지원 GPU (빠른 학습/추론 권장)



📦 라이브러리 설치:

pip install torch torchaudio numpy matplotlib librosa IPython

⚙️ 설정 방법





저장소 클론:

git clone https://github.com/JIMIN-SONG-1/DeepSpeech.git
cd DeepSpeech



LibriSpeech 데이터셋 📊:





DeepSpeech.ipynb와 Listen Attend Spell.ipynb 실행 시 자동 다운로드.



또는 OpenSLR에서 수동 다운로드.



Tacotron 2 체크포인트 🔑:





tacotron2_statedict.pt와 waveglow_256channels.pt를 프로젝트 루트에 배치.



waveglow/ 디렉토리가 inference.ipynb에서 참조 가능해야 함.



💡 팁: 가상환경(venv 또는 conda) 사용을 권장하여 라이브러리 충돌을 방지하세요!



🎮 실행 방법

1️⃣ DeepSpeech2 실행





노트북 실행:

jupyter notebook DeepSpeech.ipynb



주요 작업:





LibriSpeech 데이터 로드 및 전처리.



DeepSpeech2 모델 학습 (기본: 1 에포크, main 함수에서 epochs 수정 가능).



테스트셋에서 WER 및 CER 평가.



실험 아이디어:





hparams에서 learning_rate, batch_size 조정.

2️⃣ Listen, Attend and Spell (LAS) 실행





노트북 실행:

jupyter notebook "Listen Attend Spell.ipynb"



주요 작업:





LibriSpeech 데이터 전처리.



LAS 모델 정의 (컨볼루션 인코더, 어텐션, GRU 디코더).



⚠️ 참고: 학습 로직 미구현. DeepSpeech.ipynb의 학습 코드를 참고해 추가 가능.



실험 아이디어:





EncoderRNN, DecoderRNN의 hidden_size, n_layers 조정.

3️⃣ Tacotron 2 추론 실행





노트북 실행:

jupyter notebook inference.ipynb



주요 작업:





체크포인트 확인 (tacotron2_statedict.pt, waveglow_256channels.pt).



text 변수 수정 (예: text = "안녕하세요, 이건 테스트 음성이에요!").



멜-스펙트로그램 및 정렬 플롯 생성, WaveGlow로 오디오 합성.



노트북에서 오디오 재생 🎧.



실험 아이디어:





다양한 한국어/영어 문장으로 창의적인 음성 합성 테스트!



📂 파일 안내







📄 파일명



📝 설명





DeepSpeech.ipynb



DeepSpeech2 모델의 데이터 로드, 전처리, 학습, 평가 (LibriSpeech 사용).





Listen Attend Spell.ipynb



LAS 모델의 인코더, 어텐션, 디코더 정의 (LibriSpeech 전처리 포함).





inference.ipynb



Tacotron 2로 텍스트에서 오디오 합성 (WaveGlow 사용).



📚 참고 자료

DeepSpeech2





📖 Digital Signal Processing Lecture



🐍 Python for Signal Processing



📊 LibriSpeech Dataset

Listen, Attend and Spell





🎓 Audio for Deep Learning



🎼 Musical Applications of Machine Learning

Tacotron 2





📄 Tacotron 2 Paper



📄 WaveGlow Paper

추가 자료





🔧 Audio Preprocessing Practice



🇰🇷 Awesome Audio Study Materials for Korean



📜 라이선스

이 프로젝트는 **MIT License**에 따라 배포됩니다. 자유롭게 사용, 수정, 공유하세요! 😊



ℹ️ 추가 정보





Tacotron 2 체크포인트: NVIDIA Tacotron 2에서 다운로드.



문의 및 피드백: 궁금한 점은 Issues에 남겨주세요!



기여: PR을 통해 기여 환영! 🌟
