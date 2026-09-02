# Privacy-Preserving-Federated-Learning-for-Wireless-Vital-Sign-Estimation

This project implements a federated learning framework for wireless vital sign estimation using a CNN-LSTM model.

Before running the code, install the required environment. It is recommended to use Python 3.10. Install the necessary packages by running:

pip install torch torchvision torchaudio
pip install flwr numpy matplotlib

To run the centralized baseline, execute:

python train_central.py

This will train the model using centralized data and automatically save results.

To run the federated learning experiment, first start the server:

python server.py

Then open three separate terminals and start three clients:

python client.py 0
python client.py 1
python client.py 2

Each client will train the model locally and communicate with the server.

If you want to save the logs, you can redirect the output to files, for example:

python server.py > results/fedavg/server.txt 2>&1

After training, you can generate result plots by editing the RESULT_DIR path in figure.py, then running:

python figure.py

The generated figures will be saved in the figures folder.

Noise injection and parameter compression can be enabled or disabled in config.py.
