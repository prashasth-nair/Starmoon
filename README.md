# Starmoon, the low-cost empathic AI device

<div align="center">
    <img src="./logo.png" alt="Starmoon-logo" width="20%"  style="border-radius: 50%; padding-bottom: 20px"/>


<!-- [![Discord Follow](https://dcbadge.vercel.app/api/server/HUpRgp2HG8?style=flat)](https://discord.gg/HUpRgp2HG8) -->
[![License: GPLv3](https://img.shields.io/badge/license-GPLv3-blue)](https://www.gnu.org/licenses/gpl-3.0.en.html)&ensp;&ensp;&ensp;
<!-- [![GitHub Repo stars](https://img.shields.io/github/stars/quivrhq/quivr?style=social)](https://github.com/quivrhq/quivr) -->
<!-- [![Twitter Follow](https://img.shields.io/twitter/follow/StanGirard?style=social)](https://twitter.com/_StanGirard) -->

</div>

What is Starmoon AI in 1 sentence.
Usecases: 1, 2, 3

[Check our Roadmap](www.starmoon.ai)
<!-- custom voice clone, RAG, agent -->

## Demo Highlights 🎥

Video

## Key features 🎯

Low-cost
Voice-enabled emotional intelligence
Open-source
Small size (as small as the Apple Watch)

## Getting Started 🚀

123

### Prerequisites 📋

1. Softwares and services:
   - Docker
   - Supabase CLI
     - Follow the instructions here to install if you haven't installed
   - Vscode and PlatformIO plugin: For firmware burning
   - OpenAI API key: For AI language models
   - Deepgram API key: For speech-to-text
   - Azure speech API key: For text-to-speech
   - Huggingface API key: For emotion recognition

2. Hardware list, you have two options:
   - Buying an assembled device [website](https://www.starmoon.app)
   - Or assemble the device yourself with off-the-shelf components:
      - Seeed Studio Xiao ESP32C6
      - Microphone (INMP441)
      - Amplifier (model)
      - Speaker (model)
      - LED light (model)
      - Button (model)
      - PCB prototype board (link) + 28 AWG wires + soldering toolset

### Software setup 🖥️

- **Step 1**: Clone the repository:

  ```bash
  git clone https://github.com/StarmoonAI/Starmoon.git && cd starmoon
  ```

- **Step 2**: Copy the `.env.example` files

  ```bash
  cp .env.example .env
  ```

- **Step 3**: Update the `.env` files
  You can manually update tokens in the `.env` file

  or use:

  ```bash
  vim .env # or emacs or vscode or nano
  ```

  Update **OPENAI_API_KEY** in the `.env` file.

- **Step 4**: Launch the project
  If you have a Mac, go to Docker Desktop > Settings > General and check that the "file sharing implementation" is set to `VirtioFS`.

  ```bash
  docker compose pull
  docker compose up
  ```

  If you are a **developer**, you can run the project in development mode with the following command: `docker compose -f docker-compose.yml up --build`

- **Step 5**: Login to the app

  - You can now sign in to the app with `admin@starmoon.app` & `admin`. You can access the Starmoon webapp at [http://localhost:3000/login](http://localhost:3000/login) and sign up an account

  - You can access Starmoon backend API at [http://localhost:8000/docs](http://localhost:8000/docs)

  - You can access Supabase dashboard at [http://localhost:54323](http://localhost:54323)
  
  - You can access Celery Flower background task dashboard at [http://localhost:5555](http://localhost:5555) (`admin@starmoon.app` & `admin`)

### Hardware setup 🧰

- **Step 0 (Optional)**: Build the device yourself (if you haven't bought the assembled device)
  - Follow the instructions here for more details on assembly

- **Step 1**: Open PlatformIO Icon (Vscode icon left sidebar)
  - Click "Pick a folder"
  - Select the location of the firmware folder in the current project.

- **Step 2**: Update the WiFi credentials and WebSocket server details in the code
  - Find the following lines in the code and update them with your information:
  - Find the WIFI host by command

    ```cpp
    const char *ssid = "<your-wifi-name>";
    const char *password = "<your-wifi-password>";
    const char *websocket_server_host = "<192.168.1.1.your-server-host>";
    const uint16_t websocket_server_port = 443;
    const char *websocket_server_path = "/<your-server-path-here>";
    const char *auth_token = "<your-auth-token-here>"; // generate auth-token in your starmoon account
    ```

- **Step 3**: Build the firmware
  - Click `Build` button in the PlatformIO toolbar or run the build task.

- **Step 5**: Upload the firmware to the device
  - Connect your ESP32 to your computer using usb.
  - Click `Upload` button to run the upload task, or `Upload and Monitor` button to run the upload task and monitor the device.
  
- **Step 6**: Hardware usage
  - Once the software and firmware are set up, you can push the button to power on the ESP32 device and start talking to the device.
  - The LED indicates the current status:
    - Off: Not connected
    - Solid On: Connected and listening on microphone
    - Pulsing: Streaming audio output (receiving from server)
  
## Updating Starmoon App 🚀

- **Step 1**: Pull the latest changes

  ```bash
  git pull
  ```

- **Step 2**: Update the migration

  ```bash
  supabase migration up
  ```


## License

123
