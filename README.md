# Speech Processing and Synthesis Project

이 저장소는 PyTorch를 사용한 음성 인식 및 합성 모델의 구현을 포함합니다. 두 개의 자동 음성 인식(ASR) 모델(`Listen, Attend and Spell` 및 `DeepSpeech2`)과 `Tacotron 2` 및 `WaveGlow`를 사용한 텍스트-음성(TTS) 추론 파이프라인이 포함되어 있습니다.

## 목차
- [프로젝트 개요](#프로젝트-개요)
- [파일 구성](#파일-구성)
- [요구 사항](#요구-사항)
- [사용 방법](#사용-방법)
  - [Listen, Attend and Spell](#listen-attend-and-spell)
  - [DeepSpeech2](#deepspeech2)
  - [Tacotron 2 추론](#tacotron-2-추론)
- [데이터셋](#데이터셋)
- [참고 자료](#참고-자료)
- [기여 방법](#기여-방법)
- [라이선스](#라이선스)

## 프로젝트 개요
이 프로젝트는 다음을 구현합니다:
1. **자동 음성 인식(ASR)**: LibriSpeech 데이터셋을 사용하여 오디오를 텍스트로 변환하는 두 모델(`Listen, Attend and Spell` 및 `DeepSpeech2`)을 제공합니다.
2. **텍스트-음성(TTS)**: `Tacotron 2` 모델과 `WaveGlow`를 사용하여 텍스트에서 멜-스펙트로그램을 생성하고 오디오를 합성합니다.

코드는 Python과 PyTorch로 작성되었으며, GPU 환경에서 효율적인 학습과 추론을 지원합니다.

## 파일 구성
- **Listen Attend Spell.ipynb**: 어텐션 메커니즘이 포함된 인코더-디코더 아키텍처를 사용하는 LAS 모델을 구현합니다.
- **DeepSpeech.ipynb**: 컨볼루션 및 리커런트 레이어를 사용하고 CTC 손실을 적용한 DeepSpeech2 모델을 구현합니다.
- **inference.ipynb**: 사전 학습된 Tacotron 2 모델을 사용하여 텍스트에서 멜-스펙트로그램과 오디오를 생성하는 TTS 추론을 보여줍니다.

## 요구 사항
- Python 3.6 이상
- PyTorch 2.7.1+cu118 또는 호환 버전
- torchaudio
- librosa
- numpy
- matplotlib
- IPython
- soundfile (오디오 백엔드용)
- Tacotron 2 추론을 위한 추가 종속성 (`inference.ipynb` 참조)

## 사용 방법

### Listen, Attend and Spell
1. Jupyter Notebook에서 `Listen Attend Spell.ipynb`를 엽니다.
2. LibriSpeech 데이터셋(`train-clean-100` 및 `test-clean`)이 지정된 디렉토리에 있는지 확인하세요.
3. 노트북 셀을 실행하여 오디오 전처리, LAS 모델 학습, Word Error Rate(WER) 및 Character Error Rate(CER)로 성능 평가를 수행합니다.

### DeepSpeech2
1. `DeepSpeech.ipynb`를 Jupyter Notebook에서 엽니다.
2. LibriSpeech 데이터셋을 위와 같이 준비합니다.
3. 노트북을 실행하여 DeepSpeech2 모델을 학습하고 평가합니다. FLAC 파일 처리를 위해 커스텀 데이터셋 로더(`LibriSpeechDataset`)가 사용됩니다.
4. 학습 진행 상황과 CER, WER 평가 결과가 출력됩니다.

### Tacotron 2 추론
1. `inference.ipynb`를 Jupyter Notebook에서 엽니다.
2. `checkpoint_path`(Tacotron 2 모델)와 `waveglow_path`(WaveGlow 모델)를 사전 학습된 모델 파일 경로로 업데이트합니다.
3. 합성할 텍스트를 `text` 변수에 입력합니다.
4. 노트북을 실행하여 멜-스펙트로그램, 정렬 플롯, 그리고 `Denoiser` 클래스를 사용한 디노이즈된 오디오를 생성합니다.

## 데이터셋
ASR 모델은 **LibriSpeech** 데이터셋을 사용합니다(`train-clean-100`은 학습, `test-clean`은 테스트용). 데이터셋은 `torchaudio.datasets.LIBRISPEECH`를 통해 `./data` 디렉토리에 자동으로 다운로드됩니다.

Tacotron 2 추론은 사전 학습된 모델을 사용하므로 별도의 데이터셋이 필요하지 않습니다.

## 참고 자료
- Digital Signal Processing Lecture: [GitHub](https://github.com/spatialaudio/digital-signal-processing-lecture)
- Python for Signal Processing: [GitHub](https://github.com/unpingco/Python-for-Signal-Processing)
- Audio for Deep Learning: [Link](https://tykimos.github.io/2019/07/04/ISS_2nd_Deep_Learning_Conference_All_Together/)
- Audio Preprocessing Practice: [GitHub](https://github.com/scpark20/audio-preprocessing-practice)
- Musical Applications of Machine Learning: [Link](https://mac.kaist.ac.kr/~juhan/gct634/)
- Awesome Audio Study Materials for Korean: [GitHub](https://github.com/keunwoochoi/awesome-audio-study-materials-for-korean)

## 라이선스
이 프로젝트는 MIT 라이선스에 따라 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.