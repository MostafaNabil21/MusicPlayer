# 🎵 Music Player

### 🛠️ Skills & Technologies

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Tkinter-GUI-FFB000?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Pygame-00A36C?style=for-the-badge&logo=pygame&logoColor=white" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/GUI%20Development-6A5ACD?style=for-the-badge" />
  <img src="https://img.shields.io/badge/File%20Handling-7E57C2?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Audio%20Playback-3949AB?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Event--Driven%20Programming-5E35B1?style=for-the-badge" />
</p>

---

## 🎧 Overview

A lightweight **desktop music player application built with Python**, featuring a graphical user interface created with **Tkinter** and audio playback powered by **Pygame Mixer**.

The application scans a specified local directory for `.mp3` files and displays them in a playlist, allowing users to select and control their music directly from the GUI.

---

## ✨ Features

* 🎵 Load local `.mp3` audio files.
* 📂 Automatically scan a configured music directory.
* 📋 Display available songs in a playlist.
* ▶️ Play selected songs.
* ⏸️ Pause and resume playback.
* ⏹️ Stop the current song.
* ⏮️ Navigate to the previous song.
* ⏭️ Navigate to the next song.
* 🎨 Dark-themed desktop interface.
* 🖼️ Custom button icons.
* 🔊 Audio playback using Pygame Mixer.

---

## 🖥️ Interface

The application provides a simple desktop music-player interface consisting of:

```text
┌──────────────────────────────────────────────┐
│                  Music Player                │
│                                              │
│  ┌────────────────────────────────────────┐  │
│  │ song_01.mp3                            │  │
│  │ song_02.mp3                            │  │
│  │ song_03.mp3                            │  │
│  │ song_04.mp3                            │  │
│  └────────────────────────────────────────┘  │
│                                              │
│              Currently Playing               │
│                                              │
│       ⏮    ⏹    ▶    ⏸    ⏭               │
│                                              │
└──────────────────────────────────────────────┘
```

---

## 🎮 Controls

| Button      | Function                                |
| ----------- | --------------------------------------- |
| ⏮️ Previous | Plays the previous song in the playlist |
| ⏹️ Stop     | Stops playback and clears the selection |
| ▶️ Play     | Plays the selected song                 |
| ⏸️ Pause    | Pauses or resumes the current song      |
| ⏭️ Next     | Plays the next song in the playlist     |

---

## ⚙️ How It Works

The application uses several Python modules to handle the GUI, filesystem operations, file filtering, and audio playback.

### 1. GUI Initialization

Tkinter creates the main application window:

```python
canvas = tk.Tk()
canvas.title("Music player")
canvas.geometry("600x800")
canvas.config(bg="black")
```

### 2. Audio Initialization

Pygame Mixer handles audio playback:

```python
from pygame import mixer

mixer.init()
```

### 3. Finding Music Files

The application searches the configured directory for `.mp3` files:

```python
pattern = "*.mp3"

for root, dirs, files in os.walk(rootpath):
    for filename in fnmatch.filter(files, pattern):
        listBox.insert("end", filename)
```

### 4. Playing a Song

When a song is selected, its filename is retrieved from the playlist and loaded into the mixer:

```python
mixer.music.load(rootpath + "\\" + listBox.get("anchor"))
mixer.music.play()
```

### 5. Playlist Navigation

The application allows navigation through the songs using the selected playlist index.

```text
Current Song
     │
     ├── Previous → Song - 1
     │
     └── Next     → Song + 1
```

### 6. Pause / Resume

The application uses Pygame Mixer to pause and resume the current track:

```python
mixer.music.pause()
mixer.music.unpause()
```

---

## 🧰 Technologies Used

### Python

The main programming language used to develop the application.

### Tkinter

Used to create the graphical user interface, including:

* Main window
* Playlist
* Buttons
* Labels
* Frames

### Pygame Mixer

Used for:

* Loading audio files
* Playing music
* Pausing playback
* Resuming playback
* Stopping playback

### OS

Used to navigate through the music directory and discover audio files.

### fnmatch

Used to filter files based on the `.mp3` pattern.

---

## 📁 Project Structure

```text
Music-Player/
│
├── MusicPlayer.py
├── prev_img.png
├── stop_img.png
├── play_img.png
├── pause_img.png
├── next_img.png
└── README.md
```

> The button image files are required by the application because they are loaded directly using `tk.PhotoImage`.

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/MostafaNabil21/MusicPlayer.git
cd MusicPlayer
```

### 2. Install Pygame

Tkinter is included with most standard Python installations. Install Pygame with:

```bash
pip install pygame
```

---

## 🎵 Configure Your Music Directory

Set the `rootpath` variable in the Python file to the directory containing your MP3 files:

```python
rootpath = "C:\\Users\\YourName\\Music"
```

For example:

```python
rootpath = "D:\\Music"
```

The application searches this directory and adds matching `.mp3` files to the playlist.

---

## ▶️ Run the Application

Run the Python file:

```bash
python MusicPlayer.py
```

The Music Player window will open and display the available MP3 files.

Select a song from the playlist and use the playback controls to control the music.

---

## 🧩 Main Functions

| Function       | Purpose                           |
| -------------- | --------------------------------- |
| `select()`     | Loads and plays the selected song |
| `stop()`       | Stops the current song            |
| `play_next()`  | Plays the next song               |
| `play_prev()`  | Plays the previous song           |
| `pause_song()` | Pauses or resumes playback        |

---

## 💡 Project Concepts

This project demonstrates practical Python programming concepts including:

* Object-oriented GUI framework usage
* Event-driven programming
* Function-based application design
* File-system traversal
* File pattern matching
* GUI widgets
* Button callbacks
* Playlist management
* Audio playback
* External Python libraries
* Local file handling

---

## 🚀 Future Improvements

Possible improvements for future versions include:

* 🔀 Shuffle mode
* 🔁 Repeat mode
* 🔊 Volume control
* ⏱️ Song progress bar
* ⏭️ Automatic next-song playback
* 📂 Browse/select music folder from the GUI
* 🎼 Support for additional audio formats
* 🖼️ Album artwork
* 🎚️ Audio volume slider
* 📝 Editable playlists
* 🔍 Song search
* 💾 Save playlists between sessions

---

## 📚 Project Learning Outcomes

Through this project, I practiced building a complete desktop application with Python by combining:

```text
Python
   ↓
Tkinter GUI
   ↓
File System Handling
   ↓
Playlist Management
   ↓
Pygame Audio Engine
   ↓
Interactive Music Player
```

The project demonstrates how Python can be used to build **interactive desktop applications that combine graphical interfaces with real-time audio functionality**.
