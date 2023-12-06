# LSTM Autoencoder for Anomaly Detection
This project trains an LSTM autoencoder on potato crop data to detect anomalies indicative of disease. The model uses reconstruction error to identify outliers that could signify the onset of a disease requiring treatment.

## Data
The data is in an Excel file with columns for weather metrics like humidity and temperature ...etc collected every day, as well as a disease label column indicating whether the first visible symptoms were spotted.
The data is split into train/validation/test sets after temporalizing into sequences of past weather measurements.


## Model 
The model architecture consists of:
* Encoder LSTM layers to compress the input time series data
* RepeatVector layer to copy the encoder output
* Decoder LSTM layers to reconstruct the input
* TimeDistributed dense layer to generate the reconstruction
The model is trained to minimize the mean squared error between the input and reconstructed output using the Adam optimizer.
## Evaluation
The model reconstruction error is used as an anomaly score.
Reconstruction error thresholds are chosen based on the precision-recall curve.
Confusion matrix, ROC AUC demonstrates model performance on classifying disease anomalies.

On potato data, the model achieves an ROC AUC of 0.96 in detecting disease onset.
# LSTM Autoencoder for Anomaly Detection on Wheat

 ## Usage
Key steps like data preprocessing, model definition, and training are reusable from the original potato code. Only the data source and reconstruction error thresholds are updated.

The model achieves ROC AUC of 0.70 on wheat 

