# Predicting Stress Hotspots in FCC Materials Using Machine Learning Models

This repository contains the code and data for a machine learning project that predicts stress hotspots in face-centered cubic (FCC) materials under uniaxial tension. The project leverages microstructural features such as texture and geometry to develop predictive models that identify regions prone to high stress.

## Project Overview

Stress hotspots in FCC materials are regions that experience higher stress compared to their surroundings under applied loads. Predicting these hotspots is crucial for understanding material behavior and improving material design.

This project uses machine learning to predict stress hotspots by:
1. Preprocessing the dataset to extract crystallographic and geometric features.
2. Applying feature selection techniques to identify the most important features for hotspot prediction.
3. Building random forest models to predict stress hotspots.
4. Evaluating the model's performance and analyzing the key features contributing to stress hotspot formation.

## Key Insights and Observations

### 1. Feature Importance
- The **Schmid factor** of the slip system emerged as the most important feature in predicting stress hotspots. Grains with a lower Schmid factor tend to form hotspots.
- **Geometric features** such as grain size, distance from grain boundaries, and proximity to triple junctions are also important. Smaller grains and grains closer to these microstructural elements are more likely to become hotspots.
- Both **texture-derived** (e.g., misorientation, slip transmission) and **geometry-derived** (e.g., grain shape, size) features contribute significantly to the predictive power of the model.

### 2. Model Performance
- The random forest model achieved an **AUC of 74.03%**, indicating that the model can predict stress hotspots with reasonable accuracy.
- The **Mixed Model** (trained on all textures) outperformed models trained separately on individual texture classes, highlighting the presence of common factors that contribute to hotspot formation across different textures.
- **Feature selection** using the FeaLect algorithm helped reduce correlation bias and improved the interpretability of the model by identifying the most informative features.

### 3. Model Limitations and Potential Improvements
- The model suffers from **bias**, as indicated by a gap between training and validation scores. This suggests that adding more descriptive features, especially **long-range geometric features**, could improve performance.
- Removing low-importance features did not significantly impact model performance, indicating that the random forest model is robust against irrelevant features.

## Data and Methodology

The dataset consists of six different textures of FCC materials under uniaxial tension. Crystallographic features like the Schmid factor and geometric features like grain size were computed for each grain in the microstructure.

### Steps Involved:
1. **Data Preprocessing**: Calculation of crystallographic and geometric features.
2. **Feature Selection**: Using the FeaLect algorithm, feature importances were computed to identify the most predictive features.
3. **Model Development**: A Random Forest model was developed and trained on the dataset to predict stress hotspots.
4. **Evaluation**: Cross-validation was used to assess model performance, and ROC-AUC curves were generated to compare the mixed and partition models.

### Tools and Libraries:
- Python
- Scikit-learn
- NumPy
- Pandas
- Matplotlib
- R for feature selection with the FeaLect algorithm

## Conclusions

- Machine learning can effectively predict stress hotspots in FCC materials by leveraging both crystallographic and geometric features.
- The performance of the random forest model demonstrates the potential of data-driven methods in materials science.
- Future work should focus on including more complex geometric features and exploring different machine learning algorithms to further improve prediction accuracy.

## How to Run the Project

1. Clone this repository to your local machine.
2. Install the required Python libraries using the following command:

   ```bash
   pip install -r requirements.txt
3. Run the Jupyter notebook provided to preprocess the data, train the model, and evaluate the results.

## References

This project is based on research from various sources, including published papers on stress hotspot prediction, machine learning in materials science, and the FeaLect feature selection algorithm.


## License

This project is licensed under the MIT License - see the LICENSE file for details.

Feel free to copy-paste and modify the content as needed!
