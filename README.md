# Spacecraft Trajectory Prediction Model

## Overview
This project stands as a remarkable integration of data engineering, analytics, and machine learning, illustrating the profound impact of these fields when synergized. It focuses on developing a predictive model that accurately forecasts spacecraft trajectories based on an array of flight parameters, epitomizing the advancements achievable through meticulous data analysis and sophisticated modeling techniques.

## Data Collection
The data is meticulously gathered from a simulated spacecraft within the KRPC environment, capturing critical flight parameters such as position, velocity, g-force, aerodynamic forces, altitude, atmospheric conditions, orientation, angular momentum, mass, thrust, and atmospheric density. This wealth of data is streamed in real time and meticulously recorded for further analysis.

We gather data from a simulated spacecraft within the KRPC environment. This data includes:

* Position
* Velocity
* G-force
* Aerodynamic forces
* Altitude
* Atmospheric conditions
* Orientation
* Angular momentum
* Mass
* Thrust
* Atmospheric density

This real-time data is meticulously recorded for further analysis.


## Data Processing
Data processing is adeptly handled through `data_connecting.ipynb`, where the raw data is transformed into a structured training dataset. Each flight session contributes to a uniquely named file that enriches `training.csv`, forming the foundation for model training. Z-score normalization is applied to standardize the dataset, ensuring zero mean and unit variance, which is instrumental in enhancing model performance.

## Data Analysis
The dataset undergoes a preliminary analysis to unravel patterns and correlations within the data. `plots.ipynb` houses an array of visualizations including pair plots and feature distributions that offer deep insights into the data's characteristics. These visual tools are invaluable for comprehending the intricacies of data and harnessing its full potential.

## Model Architecture
The predictive model boasts a multi-layered architecture with various configurations:
- **Model 1**: Employs a dense network with ReLU activation functions.
- **Model 2 & 3**: Utilize LSTM networks to interpret temporal sequences derived from Model 1.
- **Model 4**: Merges the outputs from Model 2 & 3, followed by additional dense layers.

The culmination of this architecture is a series of linear activations that represent the spacecraft's predicted trajectory.

## Compilation and Training
`position_est.ipynb` serves as the epicenter for model training. The growing dataset currently features 11,772 data points with ongoing expansions. The model utilizes an Adam optimizer alongside a mean squared error loss function during training to refine accuracy and diminish prediction errors.

## Model Evaluation
The model's evaluation metrics are testament to its precision:
- Loss: 1.4339e-04
- Accuracy: 99.66%

These figures reflect the model's exceptional capability in predicting trajectories with high fidelity.

---

## Detailed Model Metrics (Refer to `model_metrics.csv` for comprehensive details)

| Model Name             | Accuracy (%)         | MSE                    | RMSE                 | MAE                   | MAPE (%)             | MPE (%)              | MedAE                | R^2 Score            | Explained Variance Score | Max Error            |
|------------------------|----------------------|------------------------|----------------------|-----------------------|----------------------|----------------------|----------------------|-----------------------|--------------------------|----------------------|
| 3dSpaceModelK.h5       | 99.99615276048316    | 3.847239516850128e-05  | 0.006202611963399    | 0.0034981260524315    | 12.85731036926011    | -2.2808764462882576  | 0.0023446138720793   | 0.9999619517076844    | 0.9999622210794264       | 0.1011146046154823   |

```
Note: Data for pos_Model6 & pos_Model7 will be incorporated upon availability.
```
Images from the project:
<table>
  <tr>
    <td><img src="https://github.com/Skizzy-create/Kerbal-Position-Estimatior/blob/main/images/actual%20vs%20predict.png" width="300"/></td>
    <td><img src="https://github.com/Skizzy-create/Kerbal-Position-Estimatior/blob/main/images/heatmap.png" width="300"/></td>
    <td><img src="https://github.com/Skizzy-create/Kerbal-Position-Estimatior/blob/main/images/loss.png" width="300"/></td>
  </tr>
  <tr>
    <td><img src="https://github.com/Skizzy-create/Kerbal-Position-Estimatior/blob/main/images/model.png" width="300"/></td>
    <td><img src="https://github.com/Skizzy-create/Kerbal-Position-Estimatior/blob/main/images/pairplot.png" width="300"/></td>
    <td><img src="https://github.com/Skizzy-create/Kerbal-Position-Estimatior/blob/main/images/regplot.png" width="300"/></td>
  </tr>
</table>
