The appliance energy prediction (AEP) task aims to forecast the total electricity usage of household appliances by analyzing past consumption data, temperature and humidity readings from different rooms, and local weather conditions. Additionally, the day of the week is added as contextual information. The AEP dataset is publicly available and contains temperature and humidity measurements from an energy-efficient house in Belgium. These readings were taken every ten minutes over a period of 4.5 months. Please refer the following for dataset details:

Candanedo, L. M., Feldheim, V., and Deramaix, D. (2017). Data driven prediction models of energy use of appliances in a low-energy house. Energy and Buildings, 140:81–97.


The following steps can be followed to get the results from CiRNN_Appl_Energy:

1. Data loading - download the provided data and define the path for the data to load it.
2. Data Preprocessing - Minmax normalisation.
3. Data preparation - This step will prepare the data so that it can be given as input to the CiRNN. It requires   specifying a sequence length.
4. Loading data into Pytorch data loaders - This step requires defining the batch size.
5. Hyperparameter tuning using Optuna - The batch size should be consistent with the above step.
6. Training - In step 5, the best hyperparameters are returned. Using these hyperparametres training can be performed.
7. Testing
