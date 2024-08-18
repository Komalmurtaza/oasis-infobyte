import pyttsx3 as p
import speech_recognition as sr

engine=p.init()
rate = engine.getProperty('rate')
engine.setProperty('rate',120)
voices = engine.getProperty('voices')
engine.setProperty('voice',voices[1].id)
print(voices)
def speak(text):
  engine.say(text)
  engine.runAndWait()

r = sr.Recognizer()
speak("hello sir i am your voice assistent. how are you?")

with sr.Microphone() as source:
    r.adjust_for_ambient_noise(source, duration=1.2)
    print("Listening...")
    audio = r.listen(source)
try:
    text = r.recognize_google(audio)
    print(f"You said: {text}")
except sr.UnknownValueError:
    print("Could not understand the audio")
except sr.RequestError as e:
    print(f"Could not request results; {e}")

import speech_recognition as sr

r = sr.Recognizer()

with sr.Microphone() as source:
    r.adjust_for_ambient_noise(source, duration=1.2)
    print("Listening...")
    audio = r.listen(source)
try:
    text = r.recognize_google(audio)
    print(f"You said: {text}")
except sr.UnknownValueError:
    print("Could not understand the audio")
except sr.RequestError as e:
    print(f"Could not request results; {e}")


if "what" and "about" and "you" in text :
        speak("i am  also having a good day sir ")
        speak("what can i do for you sir ")
