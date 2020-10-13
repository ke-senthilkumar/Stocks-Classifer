# Stocks-Classifer

This reposity is a clone of the https://github.com/cderinbogaz/inpredo It was difficult to run the python code and required a lot of code modifictions, possibly due to *nix to Windows porting.

Code has been modified so that no syntax error happens and runs in Winpython. The program can be run in 2 modes, using keras or tensorflow. For some reason, if it has Tensorflow installed, the Plaidml module doesnt work. However, with Plaidml, one can easily use their GPU for calcualtions and make it faster. If one doesn't have GPU, then Tensorflow is to be installed and Plaidml to be uninstalled. 

# Classification

The idea is to use the 1h, 4h or 1D data of a stock, create candles from them, draw a SMA on the candle and convert this data into an image. Then slide the datawindow every 7 such candles (7 1H candle in a day). And create lots and lots of images.Based on the SMA, the program classify these images and puts them as BUY or SELL. This is done by the file graphwerk.py. You can modifiy the code to suit the nunmber of candles depending on your intent. Once the images are created, 10-20% of the images from the BUY and SELL folders should be cut & copied to another foder \validation

# Training

Training of the BUY and SELL images is carried out by the Keras ML module. We dont have to bother so much about the learning process as the Keras module handles it internally. After enough number of epoch the training learns enough info and stores them. On each run of an epoch, the program verifies if the account size increases or decreases. If its an incresae, then the weight and model info is saved. This info can be used in the validation & test process.

# Test

The predict-binary.py file can be used to test or validate an image for a future buy or sell. The code has been modified so that the file name is also recorded whether its a buy or sell or no action for the files located in validation folder.

One can use a single image also to predict whether its a buy/sell/no action .

CAUTION: Trade with your own risk. The idea of the project is to understand ML and how to use classifiers for stock recommendation. 
