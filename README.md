# EMOTIW-2015

## Task
To detect the emotion of actors using a video and classify them into the 8 universal emotions.

---

## Methodology

### Preprocessing
- Features were extracted for:
**300 videos** from the train set
 **120 videos** from the test set
- **Reason for data reduction**: Every alternate video from both the sets is considered to remove repetition of data. This was done due to large dataset size and to allow faster computations.

---

## Models

### 1st Model
- **Data Preprocessing**: Face activation and padding to match the number of frames for all video files.
- **Feature Extraction**: Local Binary Pattern (LBP) features extracted.
- **Model**: SVM with a custom chi-square kernel.

### 2nd Model
- **Data Preprocessing**: Same as the 1st model.
- **Model**: SVM with radial basis function (RBF) kernel.
  - Hyperparameter tuning performed using grid search.

---

## Results

| Model          | Accuracy |
|----------------|----------|
| 1st Model (chi2 Kernel) | 10.83%   |
| 2nd Model (RBF Kernel) | 22.5%    |

---

## Analysis

### Reasons for Low Accuracy
1. **Low Amount of Data**: Low amount of labelled facial data and the amount considered in this run which contributes to the low accuracy.
2. **Data Imbalance**: Data imbalance as seen from the confusion matrix and feature graphs can also be a reason for low accuracy. 
3. **Preprocessing Limitations**:Preprocessing methods in teh paper involve face detection and alignment (aligning the eyes). The paper suggests using Intraface(unavailable now) to detect fiducial points, leading to removal of some information during feature extraction.
4. **Model Choice**:Also, the paper mentions that the winning team used CNN model, so other models might give a better accuracy than non linear chi2 kernel SVM 

---

## Conclusion
The proposed model alongwith the involved preprocessing methods yielded suboptimal results. Better results might be yielded using a more advanced models like CNN with better data preprocessing techniques. 

