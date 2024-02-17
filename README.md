# Motorola Internet Control

## Overview

This project implements an audio relay system using Python, sockets, and the PyAudio library. It allows audio transmission between a server and a client using the ngrok tunneling service.

## Prerequisites

- Python 3.x
- PyAudio
- ngrok account (for creating tunnels)

## Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/japjeet01/Motorola_Project
    cd Motorola_Project
    ```

2. Install required Python packages:

    ```bash
    pip install pyaudio pynput pydub
    ```


## Usage

### Server

1. Open a terminal and navigate to the project directory (Motorola_Project).

2. Run the server:

    ```bash
    python server.py
    ```
3. In new Terminal execute command
   
    ```bash
    ngrok config add-authtoken 2bOgoQUJHNBosKe7HjIFh1dG8x7_bJoihnxs5wkMPTBMeg8v 
    ```
4. Now execute this command to run the Ngrok server.
  
    ```bash
    ngrok tcp --region=in --remote-addr=1.tcp.in.ngrok.io:20434 6000 
    ```


### Client (Mobile App)

1. Install the  app on your mobile device.

2. Open the app and click on connect to server

3. Transmit your voice using push to talk button

4. You can start and stop recording from the recording button  and recording will be saved in Downloads directory.

5. You can access the call logs in call logs menu.


### Client (Mobile App) Indications:

1. Server Not Running :  The ngrok server is not running,

2. Channel Busy : Someone is alrealdy using the channel.

3. Receiving : you are receiving audio which is being transmitted from another motorola.

4. Transmitting : You are Transmitting the audio from mobile app to other motorola.



## Configuration

- Modify `server_ip` and `server_port` in `server.py` if needed.

- Adjust the PyAudio settings (e.g., `FORMAT`, `CHANNELS`, `RATE`, `CHUNK`) in `server.py` according to your requirements.

## Troubleshooting

- If you encounter issues with audio playback or recording, check the PyAudio documentation and ensure that your microphone and speaker settings are configured correctly.

- For ngrok-related issues, refer to the ngrok documentation or community forums.

