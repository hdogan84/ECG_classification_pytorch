Heartbeat Classification
==============================
In this project, a PyTorch implementation to predict the ECG heartbeat patterns and abnormalities is presented. The work is based on the Kaggle ECG Hearbeat Categorization Dataset. We can show that, even with simple Models, high accuracy scores on predicting either the class of the overall heartbeat pattern shape or the binary distinction between a normal or abnormal heartbeat pattern shape are possible. Using Neural Networks, we achieve high accuracy scores. Based on these initial findings, further studies can be conducted to examine this distinct behavior of neural networks in the field of detecting ECG heartbeat patterns.


Project Organization on Github
------------

    ├── LICENSE
    ├── README.md          --> This readme file
    ├── data               --> Folder for big files (only locally   
    │   │                      available).
    │   └── KAGGLE_datasets --> Datasets directly downloaded from Kaggle
    │
    ├── models             --> The models produced by the notebook code.
    │   └── DL_Models      --> Deep Learning Models
    │
    ├── notebooks          --> The finalized Jupyter notebooks.
    │   └── result_csv_files --> helper files to build the figures.
    │
    ├── references         --> The references we used for the project.
    │
    ├── reports            --> Our created reports (.pdf) and summary 
    │   │                      excel.
    │   └── figures        --> Generated figures and classification  
    │                          reports.
    │
    ├── requirements.txt   --> The requirements to run the Notebooks
    │
    └── src                --> This folder is practically not used right now.  


## How to use the Github repo / the notebooks
All code is stored in Jupyter notebooks. The notebooks contain code to directly download the necessary datasets via the KaggleAPI. This code is more or less bulletproof, but it could be necessary that one either authenticates via a webbrowser or changes the source code to make the authentification work on Kaggle. Since the datasets are quite big, they are stored in the data folder, which is created on the first run of any of the notebooks. This data is available only on the local machine and is not pushed onto github.

After initlally downloading the datasets, the notebooks all follow the same path.

1. Notebook1: Data exploration, Data Vizualization and Preprocessing:
In this notebook we show how the initial checks for data quality are performed. We produce many plots to observe the data structure. We also try out some data resampling techniques that are used in later notebooks. All plots are stored in the figures folder. Inside the figures folder, we store the datavizualization plots in a subfolder called viz_plots. This notebook is also used to generate the result plots for our reports. We therefore manually concated our final results into .csv files. These result files are stored in notebooks/result_csv_files. Notebook 1 uses those .csv files to generate the result plots, which are then stored in the figures/result_plots folder.
First, if not already happened, the Datasets are downloaded from Kaggle. Then the necessary datasets for each notebook are loaded, in case of PTBDB the reshuffling from Notebook 1 is performed.
We use switches for the configuration of the dataset sampling and to decide, which of the models shall be trained and evaluated. After deciding on the options, the selected models are trained with the configured dataset. A function to save the model (.pkl) and the classification report is always called after each successfull model training.

3. Notebooks 3a / 3b: Essentially the same as 2a / 2b but for the Deep learning models. Aside from general switches to configure datasets and model training, we implement configuration classes for each model to easily manipulate the parameters for our experiments. We implemented three DL Models:
    1. Simple_ANN
    2. Simple_CNN
    3. Advanced_CNN

    We save all model weights for each experiment and also lossplots and validation accuracy plots (/figures folder).

All Notebooks are designed to run in one go out of the box. With the configuration switches one can choose which models to run with which configurations.

-------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
