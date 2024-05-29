The task is short-term traffic speed prediction where weather data is used as contextual information for learning CiRNN.The data is available in three different folders: part1, part2, and part3. During model training the data from these folders are required to be combined. We utilized the publicly available Metr-LA real traffic dataset, which aggregates recorded traffic speeds into five-minute intervals. This dataset comprises information from 207 sensors placed throughout Los Angeles County’s highway from March 1 to June 30, 2012, and includes various details such as timestamp, travel direction, district name, lane type, segment length covered by each sensor (station), total flow, average occupancy, and average speed [1]. For our model, we focused solely on average speed. Hourly weather data, including temperature, precipitation, and wind speed, was obtained from the NASA Prediction Of Worldwide Energy Resources (POWER) database [2]. The following are the data sources:

[1] Li, Y., Yu, R., Shahabi, C., and Liu, Y. (2018b). Diffusion convolutional recurrent neural network: Data-driven traffic forecasting. https://doi.org/10.48550/arXiv.1707.01926.

[2] https://power.larc.nasa.gov/

The three folders part1, part2, and part3 consist of processed data where sensor and weather data are merged. The processed data consists of the following features : 'Year', 'Month', 'Day', 'Hour', 'Weekday', 'StationId', 'AvgSpeed', 'AvgSpeed1', 'AvgSpeed2', 'AvgSpeed3', 'AvgSpeed4', 'AvgSpeed5', 'AvgSpeed6', 'AvgSpeed7', 'Precipitation', 'Temp', 'WindSpeed'
Here, the AvgSpeed is to be predicted at time step t+k, using weather data and AvgSpeed at time t, and AvgSpeed1...AvgSpeed7. For example, to predict traffic speed on Sunday 09:00-10:00, the input would consist of Sunday 08:00-09:00 (one hour before, same day) and the previous week’s Sunday to Saturday 09:00- 10:00 traffic data (periodic data).

To run the scripts, apart from standard libraries, installation of optuna framework for hyperparameter framework will be required. The following steps can be followed for each of the scripts:

1. Data loading - download the provided data and define the path for the data to load it. Save all the files from part1, part2, and part3 in one folder. 
2. Data Preprocessing - Minmax normalisation. 
3. Data preparation: This step will prepare the data so that it can be given as input to the CiRNN. It requires specifying a sequence length.
4. Loading data into Pytorch data loaders - This step requires defining the batch size.
5. Hyperparameter tuning using Optuna - The batch size should be consistent with the above step.
6. Training - In step 5, the best hyperparameters are returned. Using these hyperparametres training can be performed.
7. Testing



