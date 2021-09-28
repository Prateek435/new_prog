import pyttsx3
import speech_recognition as sr 
import datetime
import wikipedia
import webbrowser
import os

engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[0].id)




def speak(audio):
    engine.say(audio)
    engine.runAndWait()
def wishMe():
    hour = int(datetime.datetime.now().hour)
    if hour>=0 and hour<12:
        speak("Good Morning!")
    
    elif hour>=12 and hour<18:
        speak("Good Afternoon!")

    else:
        speak("Good Evening!")

    speak("hii i am your assistant, please tell me how may i help you Sir?")


def takeCommand():
    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("listning...")
        r.pause_threshold = 1
        audio = r.listen(source)

    try:
        print("recognizing...")
        query = r.recognize_google(audio, language='en-in')
        print(f"user said:{query}\n")
    
    except Exception as e:
        #print("e")

        print("Say that again please...")
        return " "


    return query
    
if __name__ == "__main__":
    wishMe()
    while True:
        query =takeCommand().lower()
        
        if 'search' in query:
            speak("searching informations...")
            query = query.replace("wikipedia", "")
            results = wikipedia.summary(query, sentences=2)
            speak("i found some informations")
            print(results)
            speak(results)

        elif 'youtube' in query:
            webbrowser.open("youtube.com")
            speak("your youtube will be open sir.")

        elif 'google' in query:
            webbrowser.open("google.com")
            speak("search hear sir, your google will be open")

        elif 'open code' in query:
            webbrowser.open("stackoverflow.com")
            speak("your code are open Sir!")


        elif 'music' in query:
            music_dir = "C:\\Users\\pc\\Music\\Playlists"
            songs = os.listdir(music_dir)
            print(songs)
            os.startfile(os.path.join(music_dir, songs[0]))

      

