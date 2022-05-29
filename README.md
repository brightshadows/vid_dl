## Prerequisite
- Must have an account associated with https://www.oreilly.com/
- Also functional with a trial account with https://www.oreilly.com/
- Mac/Linux Environment

## Getting started
1. git clone this repo
2. change to the cloned directory:
```
cd vid_dl
```
3. Update the `batch-file.txt` with the URL of the video from https://www.oreilly.com/.
Sample URL format to populate the `batch-file.txt`

```
https://learning.oreilly.com/videos/bash-shell-scripting/9780137689064/

```
4. Make the file `yt-dlp.sh` executable

```
chmod +x yt-dlp.sh
```

5. Once completed execute the command below (whilst in the `vid_dl` directory) to automate the DL.
```
./yt-dlp.sh -u <EMAIL_OREILLY_ACCOUNT> -p <PW> -a batch-file.txt -o '%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s'
```
Where the following notation are:
* **-u** specify email account that is associated https://www.oreilly.com/
* **-p** password use to login oreilly
* **-a** specify the path to `batch-file.txt`
* **-o** this specifies the particular format to rename the videos. Recommended to not modify this.
Sample command:
```
./yt-dlp.sh -u hello-world@hotmail.com -p hello! -a batch-file.txt -o '%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s'
```

Expecta similar output below:

```
[debug] System config: ['-i', '-v', '-c', '--no-warnings', '--console-title', '--batch-file=batch-file.txt', '-o', '%(playlist_title)s/%(playlist_index)s-%(title)s.%(ext)s', '-f', 'best[tbr<=1000]/worst[[height>=720]]/best[[height<720]]']
[debug] User config: []
[debug] Custom config: []
[debug] Command-line args: ['-u', 'PRIVATE', '-p', 'PRIVATE', '-a', 'batch-file.txt', '-o', '%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s']
[debug] Batch file urls: ['https://learning.oreilly.com/videos/bash-shell-scripting/9780137689064/']
[debug] Encodings: locale UTF-8, fs utf-8, out utf-8, pref UTF-8
[debug] youtube-dl version 2021.06.06
[debug] Git HEAD: 801958b7c
[debug] Python version 3.8.5 (CPython) - macOS-10.16-x86_64-i386-64bit
[debug] exe versions: none
[debug] Proxy map: {}
[safari:course] Downloading login page
[safari:course] Logging in
[safari:course] Completing login
[safari:course] 9780137689064: Downloading course JSON
[download] Downloading playlist: Bash Shell Scripting, 2nd Edition
[safari:course] playlist Bash Shell Scripting, 2nd Edition: Collected 126 video ids (downloading 126 of them)
[download] Downloading video 1 of 126
[safari:api] Downloading login page
[safari:api] 9780137689064/BSS2_00_00_00: Downloading part JSON
[safari] Downloading login page
[safari] 9780137689064-BSS2_00_00_00: Downloading kaltura session JSON
....
```