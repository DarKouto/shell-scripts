# 🖥️ Shell Scripts

This repository contains a set of bash/shell scripts that automate several tasks that I had to do in my personal workflow.
Most of the code and the prompts in these scripts are in Portuguese, because, well I'm Portuguese and these are my scripts, so deal with it.
The scripts work on **BASH** and **ZSH**, and should also work on any **POSIX** Standard Shell. Tested on CachyOS Linux (Arch Based Distro).

## 🛠️ Installation
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
<hr>

## 🚀 The Scripts and Usage

### **Split Video: `dividir-video`**
- Requirements: `ffmpeg`

This script uses `ffmpeg` to quickly split video files larger than 4GB into two or more files without any losses. Essential for bypassing the 4GB file size limit on FAT32 formatted drives, that are required to use in legacy hardware (like TV's).
It automatically detects the extension (MKV/MP4) and the duration of the video. If the video is shorter than 4 hours, it splits it into 2 different parts. If the video is longer than 4 hours, it splits in several 1-hour parts.

### Video Codec Converter: `converter-video`
- Requirements: `ffmpeg`

Transcodes H.265 (HEVC) videos to H.264 MP4 with a clean output.
    * *Use Case:* Fixes playback issues on older Smart TVs and devices that do not support modern H.265 codecs.

### Download YouTube Videos: `sacar-youtube`
- Requirements: `firefox` and `yt-dlp` https://github.com/yt-dlp/yt-dlp

Downloads YouTube videos directly into MP4 format and H264 codec for better compatability, uses Firefox cookies to prevent bot detection and ensure high-speed downloads.

### Copy Music to USB in Alphabetical Order: `musica-iveco`
Specialized audio extraction and normalization script.
    * *Use Case:* Prepares audio files for in-vehicle entertainment systems, ensuring consistent volume and format compatibility.
