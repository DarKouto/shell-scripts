# 🖥️ Shell Scripts

This repository contains a set of bash/shell scripts that automate several tasks that I had to do in my personal workflow.

I used ```#!/usr/bin/env bash``` as **Shebang** for better compatibility across different systems, and because it's the **Best Practice**.

All the scripts follow the **POSIX Standard**, and were tested on **CachyOS** (Arch Linux Based Distro).

Most of the code, as well as the prompts are written in Portuguese. That's because I'm Portuguese and these are my scripts, for my workflow, so *deal with it*. Consider yourself lucky that I've even bothered to write the README in English 💀

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
sudo cp {dividir-video,converter-video,sacar-youtube,musica-iveco} /usr/local/bin/
```

<hr>

## 🚀 The Scripts

## ✂️ `dividir-video`: Splits Video Files in a Fast and Lossless way
- Requirements: `ffmpeg`

**Use Case:** Most legacy hardware (like TV's) only support FAT32 formatted USB drives. Since the per-file limit of FAT32 is 4GB, I needed something to split large video files into two or more smaller files, quickly and without losses in quality. I used `ffmpeg`'s -segment flag in this script.

In addition, it automatically detects the video's duration and extension (MKV/MP4). If the video is shorter than 4 hours, it splits it into 2 different parts. If the video is longer than 4 hours, it splits in 1-hour parts.

### Usage:
- Place the video you want to split in a dedicated folder:
- Open a Terminal in that very same folder and type:
```bash
dividir-video
```
The script will now create two (or more) new files and name then accordingly, while preserving the original video file.

<hr>

## 🔃 `converter-video`: Converts H.265 Videos to H.264 MP4 Format
- Requirements: `ffmpeg`

**Use Case:** Most legacy hardware (like TV's) don't support the H.265 codec or the .MKV extension. This script uses ```ffmpeg```'s libx264 library to convert the video file into H.264 cocec and .MP4 extension while maintaining a clean output.

### Usage:
- Place the video you want to convert in a dedicated folder
- Open a Terminal in that very same folder and type: ```bash converter-video ```

The script will now convert your H.265 video into MP4 H.264, while preserving the original video file.

<hr>

## ⬇️ sacar-youtube: Downloads YouTube Videos
- Requirements: `firefox` and `yt-dlp` https://github.com/yt-dlp/yt-dlp

Uses yt-dlp` to download YouTube videos directly into MP4 format and H264 codec for better compatibility, uses Firefox cookies to prevent bot detection and ensure high-speed downloads.

### Usage:
- Open Terminal and type:
```bash
sacar-youtube
```
Then just paste the URL of the video you want to download.

<hr>

## 🎵 `musica-iveco`: Copies Music to USB Drive in Alphabetical Order
This one is is a very pecicular **edge case**. I have a **IVECO Daily** van that I use for work. The radio has a USB Port to play MP3 files.

**The problem**: the radio sorts the MP3 files by transfer date and not by alphabetical order, which leads to the tracklists being complepety shuffled. **SHAME ON YOU IVECO** (it's a really good vehicle btw, but this issue with the radio is complete ASS. I don't care, sue me.)

**The solution**: using this script which forces the files to be transferred to the USB Drive in an alphabetically orderly fashion. **AS GOD INTENDED**. It uses a simple *for loop* with the -r recursive flag to make sure folders and subfolders are copied.

### Usage:
**IMPORTANTE NOTE:** My USB Drive path is "/run/media/darkouto/PEN_IVECO/", in your case it should be different, be sure to edit the script file to match your own USB Drive path
- Place the MP3 files you want to transfer in a dedicated folder. Preferably each album in its own folder.
- Open a Terminal in that folder and type:
```bash
musica-iveco
```
Wait for the process to finish and you're done.
