# Shell Scripts Toolkit 🛠️

This repository contains a set of bash/shell scripts that automate several tasks that I had to do in my personal workflow.
Most of the code and the prompts in these scripts are in Portuguese, because, well I'm Portuguese and these are my scripts, so deal with it.
The scripts work on **BASH** and **ZSH**, and should also work on any **POSIX** Standard Shell.

## 🚀 The Scripts

**Split Video: dividir-video**
Automatically detects and splits large video files (MKV/MP4) into 4GB chunks using `ffmpeg`. 
    * *Use Case:* Essential for bypassing the 4GB file size limit on FAT32 formatted drives used in legacy hardware.

**Video Codec Converter: converter-video**
Transcodes H.265 (HEVC) videos to H.264 MP4 with a clean output.
    * *Use Case:* Fixes playback issues on older Smart TVs and devices that do not support modern H.265 codecs.

**Download YouTube Videos: sacar-youtube** **`sacar-youtube`**
A streamlined wrapper for `yt-dlp`.
    * *Use Case:* Downloads YouTube videos directly into MP4 format, utilizing Firefox cookies to prevent bot detection and ensure high-speed downloads.

**Copy Music to USB in Alphabetical Order: `musica-iveco`**:
Specialized audio extraction and normalization script.
    * *Use Case:* Prepares audio files for in-vehicle entertainment systems, ensuring consistent volume and format compatibility.

## 🛠️ Installation & Usage

To use these scripts globally in your system:

1. **Clone the repository and cd into it:**
```bash
git clone https://github.com/darkouto/shell-scripts.git
cd shell-scripts
```

2. **Grant execution permissions:**
```bash
sudo chmod +x *
```

3. **Move the scripts to your local bin folder:**
```bash
sudo cp * /usr/local/bin
```
