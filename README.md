# 🖥️ Shell Scripts

This repository contains a set of bash/shell scripts that automate several tasks that I had to do in my personal workflow.

I used ```#!/usr/bin/env bash``` as **Shebang** for better compatibility across different systems, and because it's the **Best Practice**.

All the scripts were written following the **POSIX Standard**, and were tested on **CachyOS** (Arch Linux Based Distro).

Most of the code, as well as the prompts are written in Portuguese. That's because I'm Portuguese and these are my scripts, for my workflow, so *deal with it*. Consider yourself lucky that I've even bothered to write the README in English 💀

## 🛠️ Installation

**Copy this command to your Terminal:**
```bash
git clone https://github.com/darkouto/shell-scripts.git
cd shell-scripts
sudo install -v -m 755 {dividir-video,converter-video,sacar-youtube,musica-iveco} /usr/local/bin/
```
This command **clones the repo** to your local machine, **changes directory** into it, then **grants execution permission** to the scripts and **copies** them to your /usr/local/bin folder, allowing you to use them in your Terminal from any working directory.

**Alternative Method**: Download the <a id="raw-url" href="https://github.com/DarKouto/shell-scripts/raw/main/instalar-scripts">instalar-scripts</a> file file, make it executable and run it.

https://github.com/DarKouto/shell-scripts/blob/main/instalar-scripts
<hr>

## 🚀 The Scripts

## ✂️ `dividir-video`: Splits Video Files in a Fast and Lossless way
- Requirements: `ffmpeg`

**Use Case:** Most legacy hardware (like TV's) only support FAT32 formatted USB drives. Since the per-file limit of FAT32 is 4GB, I needed something to split large video files into two or more smaller files, quickly and without losses in quality. I used the `ffmpeg` -segment flag in this script.

In addition, it automatically detects the video's duration and extension (MKV/MP4). If the video is shorter than 4 hours, it splits it into 2 different parts. If the video is longer than 4 hours, it splits in 1-hour parts.

### Usage:
- Place the video file you want to split in a dedicated folder.
- Open a Terminal in that folder and type:
```bash
dividir-video
```
The script will now create two (or more) new files and name then accordingly, while preserving the original video file.

<hr>

## 🔃 `converter-video`: Converts H.265 Videos to H.264 MP4 Format
- Requirements: `ffmpeg`

**Use Case:** Most legacy hardware (like TV's) don't support the MKV extension nor the H.265 codec (even on MP4 files). This script uses the ```ffmpeg``` libx264 library to convert the video file into the H.264 cocec and the MP4 extension while maintaining a clean output.

### Usage:
- Place the video file you want to convert in a dedicated folder.
- Open a Terminal in that folder and type:
```bash
converter-video
```

The script will now convert your H.265 video into H.264 in MP4, while preserving the original video file.

<hr>

## ⬇️ `sacar-youtube`: Downloads YouTube Videos
- Requirements: `firefox` and `yt-dlp`

Uses `yt-dlp` to download YouTube videos directly into MP4 format and H.264 codec for better compatibility. I've added the flag `--cookies-from-browser firefox` to prevent bot detection and ensure high-speed downloads. If you use a different browser, refer to the official `yt-dlp` documentation to see how to edit the script: https://github.com/yt-dlp/yt-dlp

### Usage:
- Open Terminal and type:
```bash
sacar-youtube
```
Then just paste the URL of the video you want to download.

<hr>

## 🎵 `musica-iveco`: Copies Music to USB Drive in Alphabetical Order
This one is is a very peculiar **edge case**. I have a **IVECO Daily** van that I use for work. The radio has a USB Port to play MP3 files.

**The problem**: the radio sorts the MP3 files by transfer date and not by alphabetical order, which leads to the tracklists being complepety shuffled. **SHAME ON YOU IVECO** (it's a really good vehicle btw, but this issue with the radio is complete ASS. I don't care, sue me.)

**The solution**: using this script which forces the files to be transferred to the USB Drive in an alphabetically orderly fashion. **AS GOD INTENDED**. 

It uses a simple *for loop*: for each folder in the PC it creates another folder with the same name in the USB Drive, and then copies the files alphabetically with the *Globbing* method for extra safety.

After this process is complete, the script runs the *sync* command to force the indexes of the USB Drive to be rewritten in the correct order. (Ex: if an album is added afterwards, this guarantees that it is placed in the correct order, and not in the end).

Finally, the script performs a cleanup to remove all indexing files and dotfiles, ensuring the drive remains organized and free of system junk.

### Usage:
**IMPORTANT NOTE:** My USB Drive path is "/run/media/darkouto/PEN_IVECO/", in your case it should be different, be sure to edit the script file to match your own USB Drive path.
- Place the MP3 files you want to transfer in a dedicated folder. Preferably each album in its own folder.
- Open a Terminal in that folder and type:
```bash
musica-iveco
```
Wait for the process to finish and you're done.
