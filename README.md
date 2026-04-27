# 🖥️ Shell Scripts

This repository contains a set of bash/shell scripts that automate several tasks that I had to do in my personal workflow.
Most of the code and the prompts in these scripts are in Portuguese, because, well I'm Portuguese and these are my scripts, so deal with it.
The scripts work on **BASH** and **ZSH**, and should also work on any **POSIX** Standard Shell. Tested on CachyOS Linux (Arch Based Distro).

## 🛠️ Installation

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

## `dividir-video`: Splits Video Files in a Fast and Lossless way
- Requirements: `ffmpeg`

I created this script because most legacy hardware (like TV's) only support FAT32 formatted USB drives. Since the per-file limit of FAT32 is 4GB, I needed something to split large video files into two or more smaller files, quickly and without losses in quality. I used `ffmpeg`'s -segment flag in this script.

In addition, it automatically detects the video's duration and extension (MKV/MP4). If the video is shorter than 4 hours, it splits it into 2 different parts. If the video is longer than 4 hours, it splits in 1-hour parts.

### Usage:
Place the video you want to split in a dedicated folder, and open a Terminal in that very same folder, then type:
```bash
dividir-video
```
The script will now create two (or more) new files and name then accordingly, while keeping the original video intact.

### `converter-video`: Converts Videos to H.264 MP4 Format
- Requirements: `ffmpeg`

Transcodes H.265 (HEVC) videos to H.264 MP4 with a clean output.
    * *Use Case:* Fixes playback issues on older Smart TVs and devices that do not support modern H.265 codecs.

### `sacar-youtube: Downloads YouTube Videos
- Requirements: `firefox` and `yt-dlp` https://github.com/yt-dlp/yt-dlp

Downloads YouTube videos directly into MP4 format and H264 codec for better compatability, uses Firefox cookies to prevent bot detection and ensure high-speed downloads.

### `musica-iveco`: Copies Music to USB Drive in Alphabetical Order
Specialized audio extraction and normalization script.
    * *Use Case:* Prepares audio files for in-vehicle entertainment systems, ensuring consistent volume and format compatibility.
