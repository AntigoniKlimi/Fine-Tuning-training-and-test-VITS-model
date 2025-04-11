
# Fine-Tuning VITS Model for High-Quality Speaker-Specific Speech Synthesis

## 1. Introduction

This project focuses on fine-tuning the VITS (Variational Inference Text-to-Speech) model to improve its performance in generating natural, high-quality speech. The training process uses the [LJSpeech](https://keithito.com/LJ-Speech-Dataset/) dataset, which contains recordings from a single female speaker, to specialize the model in synthesizing speech that closely mimics the target voice.

## 2. Objective

The primary goal was to adapt a pre-trained VITS model to generate speech that replicates the voice characteristics of one specific female speaker. The model was fine-tuned using data from both male and female voices (with different timbres) in order to learn how to convert their voice features into the target speaker’s style. This speaker adaptation helps in reducing variability and leads to better generalization over speaker-specific traits.

## 3. Methodology

### 3.1 Dataset

- **Source**: LJSpeech dataset, obtained via Kaggle.
- **Content**: High-quality recordings of English utterances by a single female speaker.

### 3.2 Data Preprocessing

- Audio normalization to ensure consistent volume levels.
- Text preprocessing and phoneme conversion using Coqui TTS tools.
- Phoneme representation (IPA) enabled better pronunciation modeling.
- Noise reduction and dynamic range compression applied for audio clarity.

### 3.3 Pre-trained Model

The base model was pre-trained on the VCTK dataset, which includes recordings from multiple speakers with diverse accents and voice characteristics. This pre-training provided a solid foundation of general speech synthesis knowledge before fine-tuning on LJSpeech.

### 3.4 Training Configuration

- **Learning Rate**: `0.0001`
- **Batch Size**: `32`
- **Epochs**: `50`
- **Training Time**: ~1 hour using GPU acceleration
- **Trainer**: Coqui TTS Trainer API with mixed precision and checkpoint saving

### 3.5 Code Workflow

1. Install dependencies (Coqui TTS and others)
2. Import required modules and functions
3. Load and preprocess LJSpeech dataset
4. Configure audio and text processors
5. Set model hyperparameters
6. Load selected data samples
7. Initialize and launch training process
8. Save the best-performing model checkpoint

## 4. Results

### 4.1 Outcome

The fine-tuned model demonstrated:

- Clearer articulation
- Enhanced naturalness
- Voice conversion accuracy, especially for transforming different speaker inputs to the target speaker’s style

### 4.2 Observations

- Male voices were successfully transformed to resemble the target female voice.
- Female voice samples that were closer to the target timbre helped accelerate convergence and improve quality.
- Fine-tuning improved performance significantly over the baseline VITS model.

## 5. Conclusion and Future Work

### 5.1 Conclusion

Fine-tuning VITS on a single-speaker dataset such as LJSpeech leads to noticeable improvements in speaker-specific TTS quality. Careful selection of hyperparameters and thorough preprocessing played a key role in achieving these results.

### 5.2 Future Directions

- Increase number of epochs for even more natural output
- Explore dialect and language switching
- Experiment with age-based voice conversions (e.g., adult ↔ child)
- Investigate cross-lingual voice adaptation and multilingual synthesis

## License

This project is for academic purposes. 

Antigoni Klimi
