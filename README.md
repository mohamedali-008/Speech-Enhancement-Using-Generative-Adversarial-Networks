# Speech Enhancement Using Generative Adversarial Networks (GANs)

## Overview

This project focuses on enhancing speech quality using **Speech Enhancement Generative Adversarial Networks (SEGAN)**. The model operates directly on raw waveforms, eliminating the need for hand-crafted audio features. It improves speech intelligibility while reducing background noise through an adversarial training approach. The proposed system leverages deep learning techniques to achieve high-fidelity speech restoration, making it highly effective for real-world applications such as telecommunications, assistive hearing devices, and automatic speech recognition systems.

## Features

- **End-to-End Learning**: Works directly on raw audio waveforms.
- **GAN-Based Enhancement**: Employs an encoder-decoder structure with skip connections.
- **Noise Reduction**: Effectively removes background noise while preserving speech clarity.
- **Pretrained on VoiceBank + DEMAND Dataset**: Trained using a combination of speech and diverse noise conditions.
- **Improved Speech Quality Metrics**: Enhancements measured by PESQ, CBAK, COVL, and STOI scores.

## Methodology

### Data Preprocessing

- Resampling to 16kHz.
- Amplitude normalization.
- Audio segmentation (1-second window, 50% overlap).

### Model Architecture

- **Generator**: Encoder-decoder structure with skip connections.
- **Discriminator**: Provides adversarial feedback using virtual batch normalization.

### Training Strategy

- Uses VoiceBank + DEMAND dataset.
- Trained adversarially using a zero-sum game between the generator and discriminator.
- Evaluated on speech quality metrics.

## Dataset

- **Training Data**: Noisy-clean speech pairs from the VoiceBank corpus mixed with DEMAND noise.
- **Testing Data**: Unseen speech samples with different noise conditions for evaluation.

## Installation

To set up the project, follow these steps:

```bash
# Clone the repository
git clone https://github.com/your-username/Speech-Enhancement-GAN.git
cd Speech-Enhancement-GAN

# Install dependencies
pip install -r requirements.txt
```

## Usage

Run the preprocessing and training scripts:

```bash
# Preprocess dataset
python preprocess.py

# Train the SEGAN model
python train.py
```

For inference:

```bash
python enhance.py --input noisy_audio.wav --output enhanced_audio.wav
```

## Results

- **PESQ Score**: Improved from 1.51 to 2.99.
- **CBAK Score**: Increased from 2.42 to 3.13.
- **COVL Score**: Enhanced from 3.29 to 4.47.
- **STOI Score**: Maintained around 0.92-0.93.

## Future Work

- Implement **CNN-GANs** for time-frequency masking.
- Optimize computational efficiency for real-time speech enhancement.
- Extend the dataset with more diverse noise conditions.

## Contributors

- **Nouran Khatab** – Model Evaluation & Analysis
- **Mohammed El-Naggar** – Core Model Implementation
- **Malak Nasser** – Preprocessing & Feature Engineering

## Acknowledgment

Special thanks to **Dr. Inas Yassine** and **Eng. Samar Alaa** from **Cairo University** for their valuable guidance and support.

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.


