# Text-to-Speech Conversion in Google Colab

📄 **Project Overview**  
This project allows you to convert any text you input into speech and save it as an MP3 file using Google Colab. It’s a simple and interactive way to turn text into audio using the **gTTS (Google Text-to-Speech)** library. Once converted, you can easily download the audio file to your computer.

🌟 **Features**  
- **Text-to-Speech Conversion**: Convert your text into natural-sounding speech using Google’s Text-to-Speech API.  
- **MP3 File Creation**: The converted speech is saved as an MP3 file.  
- **Download Option**: Download the MP3 file directly from Google Colab to your computer.

🛠 **Libraries Used & Why**  
- **gTTS (Google Text-to-Speech)**: This is the core library used to convert text into speech. It’s fast, simple, and supports multiple languages.  
  - **Installation**:  
    ```bash
    !pip install gtts
    ```
  - https://gtts.readthedocs.io/en/latest/ 
- **pydub**: A versatile audio library that can be used for converting and manipulating audio files. In this project, it’s optional, but useful for future enhancements like audio format changes.  
  - **Installation**:  
    ```bash
    !pip install pydub
    ```
- **Google Colab’s `files` Module**: This is used to download the MP3 file from Colab to your local machine. Since Colab doesn’t have direct audio playback, this method lets you save your speech file for personal use.  

📜 **How the Code Works**  

1. **Import Libraries**: We import `gTTS` to handle text-to-speech, `pydub` (though not mandatory), and Colab’s `files` module to download the file.
   ```python
   from gtts import gTTS
   from pydub import AudioSegment
   import os
   from google.colab import files

# Text-to-Speech Function: This function takes your text input, converts it into an MP3 file using gTTS, and then triggers the download so you can get the file.
def text_to_speech_and_save(text, filename="results.mp3"):
    """Converts text to speech and saves it as an MP3 file."""
    tts = gTTS(text=text, lang='en')
    tts.save(filename)
    print(f"Audio saved as '{filename}'")
    files.download(filename)

# User Input: The script asks for user input and processes the text, converting it into an MP3 file called results.mp3.
if __name__ == "__main__":
    user_input = input("Enter the text you want to convert to speech: ")
    text_to_speech_and_save(user_input, filename="results.mp3")

📥 Example Walkthrough

Input: "Hello, welcome to our text-to-speech demo!"
Output: An MP3 file named results.mp3 is created with the spoken version of the input text.
Download: A download link is provided to save the file to your computer.

📚 Further Reading and Resources

gTTS (Google Text-to-Speech) Documentation: Learn more about gTTS and its capabilities. https://gtts.readthedocs.io/en/latest/
pydub Documentation: Explore how you can manipulate audio files in various formats using pydub. https://projector-video-pdf-converter.datacamp.com/17718/chapter3.pdf

🚀 Why Use This Project?

This project is perfect for anyone looking to easily convert text into speech without needing advanced audio tools or programming knowledge. With just a few clicks, you can have your own audio files ready for personal or professional use!
