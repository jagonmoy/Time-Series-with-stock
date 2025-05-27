# How to run the Stock Forecasting Script in your machine. 

## Step 1: Clone the repository

if you have SSH key, you can clone the repository using the following command:
```bash
git clone git@github.com:jagonmoy/Time-Series-with-stock.git
```

if you don't have SSH key, you can clone the repository using the following command:
```bash
git clone https://github.com/jagonmoy/Time-Series-with-stock.git
```


## Step 2: Install the dependencies

Please be careful about the torch version which needs to be compatible with the version of CUDA/GPU installed in your machine. For me the the working torch version is 2.4.1+cu118. So, I have update the requirements.txt file with the compatible torch version of mine.
<br><br>
So, please update the requirements.txt file with the compatible torch version. then run the following command to install the dependencies:
```bash
pip install -r requirements.txt
```

## Step 3 : Download the data and put it in the dataset folder

Download the data from the following link:
https://www.kaggle.com/datasets/paultimothymooney/stock-market-data

Download the data and put it in a folder named **"dataset"** in the root directory.


## Step 4: Evaluate the Script before running it

- Please change the variable **CUDA_VISIBLE_DEVICES** in the script to the GPU number you want to use. For example, if you want to use the GPU number 0, you can set it to **export CUDA_VISIBLE_DEVICES=0**
<br><br>
- **enc_in, dec_in, c_out** they are set to 7 because the dataset has 6 columns and I have add the 7th column for company code.
<br><br>
- Adjust the **seq_len, label_len, pred_len, factor, d_model, d_ff,itr, train_epochs, batch_size, num_workers** according to your machine configuration and the time you want to run. I have set them minimal to run this script on my local machine.

## Step 4: Run the script

```bash
bash scripts/long_term_forecast/Stock_script/TimesNet_Stock.sh
```

## Step 5: Check the result
result will be save in the **test_results** folder, **results** folder, **results_long_term_forecast.txt** file. you will also find a **checkpoints** folder after the training is complete. 




