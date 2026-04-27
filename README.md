# Shell Scripts Toolkit 🛠️

Various Shell Scripts that automate several tasks

## 🚀 The Scripts

This repository contains a set of "wrappers" and automation scripts built to streamline my workflow:

* **`dividir-video`**: Automatically detects and splits large video files (MKV/MP4) into 4GB chunks using `ffmpeg`. 
    * *Use Case:* Essential for bypassing the 4GB file size limit on FAT32 formatted drives used in legacy hardware.
* **`converter-video`**: Transcodes H.265 (HEVC) videos to H.264 MP4 with a clean output.
    * *Use Case:* Fixes playback issues on older Smart TVs and devices that do not support modern H.265 codecs.
* **`sacar-youtube`**: A streamlined wrapper for `yt-dlp`.
    * *Use Case:* Downloads YouTube videos directly into MP4 format, utilizing Firefox cookies to prevent bot detection and ensure high-speed downloads.
* **`musica-iveco`**: Specialized audio extraction and normalization script.
    * *Use Case:* Prepares audio files for in-vehicle entertainment systems, ensuring consistent volume and format compatibility.

## 🛠️ Installation & Usage

To use these scripts globally in your system:

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/darkouto/shell-scripts.git](https://github.com/darkouto/shell-scripts.git)
   ```
