Estimating the Remaining Useful Life (RUL) is a crucial aspect of prognostics. RUL indicates the duration remaining before a failure is likely to occur, based on the machine's current age, condition, and operational history. The code presents CiRNN models developed using well known NASA Turbofan Engine Degradation Simulation Data Set. The details are avilable in 
R. Dutta Baruah and M. Muñoz Organero, "Explicit Context Integrated Recurrent Neural Network for Sensor Data Applications" , Preprint available at http://arxiv.org/abs/2301.05031
The dataset consists of four different datasets FD001, FD002, FD003, and FD004 which have data from 21 sensors, 3 operational settings along wiht engine identification number, and cycles of each engine. 
FD001 has 1 failure mode and 6 operational states, FD002 has 1 failure mode and 6 operational conditions, FD003 has 2 failure modes and 1 operating condition, finally, FD004 has 2 failure modes and 6 operating states. The operational settings consistute the contextual information. 

Seprate scripts are created for four datasets, which are CiRNN_FD001.ipynb, CiRNN_FD002.ipynb, CiRNN_FD003.ipynb, CiRNN_FD004.ipynb, respectively. To run the scripts, apart from standard libraries, installation of optuna framework for hyperparameter framework will be required. The following steps can be followed for each of the scripts:
1. Data loading - download the provided data and define the path for the data to load it.
2. Data Preprocessing - For FD001 and FD003 where there is only one operational condition, contextual normalisation using clustering is not required. They require ony min-max normalization. On the other hand, for FD002 and FD003, two preprocessing methods are used, contextual normalisation using clustering and min-max normalisation. So, two different models will be developed depending on the preprocessed data. More details are available in the above mentioned reference. After normalisation, data smoothing is performed. 
3. Data preparation: This step will prepare the data so that it can be given as input to the CiRNN. It requires specifying a sequence length.
4. Loading data into Pytorch data loaders - This step requires defining the batch size.
5. Hyperparameter tuning using Optuna - The batch size should be consistent with the above step.
6. Training - In step 5, the best hyperparameters are returned. Using these hyperparametres training can be performed.
7. Testing- Testing can be peformed in two ways, engine -wise or considering entire test data. In the mentioned paper the testing is performed engine-wise. 


