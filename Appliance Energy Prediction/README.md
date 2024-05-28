The appliance energy prediction (AEP) task aims to forecast the total electricity usage of household appliances by analyzing past consumption data, temperature and humidity readings from different rooms, and local weather conditions. Additionally, the day of the week is added as contextual information.

The following steps can be followed for each of the scripts:

Data loading - download the provided data and define the path for the data to load it.
Data Preprocessing - For FD001 and FD003 where there is only one operational condition, contextual normalisation using clustering is not required. They require ony min-max normalization. On the other hand, for FD002 and FD003, two preprocessing methods are used, contextual normalisation using clustering and min-max normalisation. So, two different models will be developed depending on the preprocessed data. More details are available in the above mentioned reference. After normalisation, data smoothing is performed.
Data preparation: This step will prepare the data so that it can be given as input to the CiRNN. it requires specifying a sequence length.
Loading data into Pytorch data loaders - This step requires defining the batch size.
Hyperparameter tuning using Optuna - The batch size should be consistent with the above step.
Training - In step 5, the best hyperparameters are returned. Using these hyperparametres training can be performed.
Testing- Testing can be peformed in two ways, engine -wise or considering entire test data. In the mentioned paper the testing is performed engine-wise.
C
