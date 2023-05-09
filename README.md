# Deep Learning Final Project
## Speech Enhancement Using Deep Learning
### A study on time vs frequency domain methods and models
Work done in google colab with PyTorch \
All the code can be found in DL_Final_Project.ipynb \
About 7.6k samples from the VoiceBank + Demand dataset used for training \
There are text commments above each section explaining what they do (unless self explanitory) \
The function of each section in order is as follows: \ 
- Load dataset from github
- Implement helper functions for audio transforms and plotting
  - STFT, DWT, STDCT and their inversions. 
  - Some wrappers as needed
- Load datasets given desired processing parameters, main ones to change:
  - Change the transform if desired (default: None yields raw waveforms)
  - Change the length of the input sample if desired (will pad or truncate)
- CRNN model implementation ( Frequency )
- Wave-U-Net model implementation ( Time )
- Block for custom loss and collate function for padding spectorgram within a batch
- Training block with train/testing functions and training/validation loop
- Testing block for inference after training use the best model params
- Asses SNR and PESQ metrics of test set results using the cleaned data and respective representation of true clean data
  - Must initialize and provide an inverse transform if the data was processed with one
  - Extra parameter for passing complex test data for attaching noisy phase if using the STFT 
- Averaging and peak computations for SNR and PESQ and visualization/listening to samples if desired
