🎧 Emotion-Aware Music Recommendation System
Turn your mood into music. This AI-powered system takes raw emotional text (like "I just got dumped and everything tastes like dust") and recommends Spotify tracks that match your emotional state—because sometimes, the algorithm understands your heartbreak better than your friends do.

🧠 What It Does
Emotion Detection
Uses state-of-the-art NLP models to analyze free-form emotional text and extract top 3 emotions (e.g., disappointment, grief, embarrassment).

Mood & Genre Mapping
Maps detected emotions to personalized moods (pensive, energetic, etc.) and then to valid Spotify genres (indie, electronic, soul... you name it).

Music Recommendation Engine
🎯 Tiered search system:

Direct genre search (Spotify API)

Public playlist fallback if no previewable tracks found

Spotify’s built-in recommendations

AI-powered keyword fallback using emotion labels as search queries

Output
A clean, clickable table of 10 recommended tracks: Title, Artist, Album, Preview, and Spotify link.

🚀 How to Run
Requirements
Python 3.8+

Spotipy

Transformers

scikit-learn

gliclass (optional, but imported)

An active Spotify Developer Account

Install Dependencies
bash
Copy
Edit
pip install spotipy transformers torch scikit-learn sentence_splitter gliclass
Setup
Create a .env or directly add:

python
Copy
Edit
SPOTIPY_CLIENT_ID = 'your_client_id'
SPOTIPY_CLIENT_SECRET = 'your_client_secret'
Make sure the Spotify app has redirect URI set to:

arduino
Copy
Edit
http://127.0.0.1:8888/callback
📦 Features
🧠 Emotion detection via bert-emotion and zero-shot-classification

🎶 24 emotion → genre mappings with fallback genres

🔁 Multi-stage Spotify search and recovery system

🪵 Full console logs of fallback behavior and failure modes

💥 Handles socket access errors gracefully (well… emotionally)

📸 Sample Output
“I got dumped and everything tastes like dust.”

yaml
Copy
Edit
Top Detected Emotions:
  disappointment: 39.3%
  disgust: 13.8%
  embarrassment: 9.6%

Mapped Mood: pensive  
Suggested Genre: indie

Recommended Songs:
- Lua – Bright Eyes
- Sweet Disposition – The Temper Trap
- What Sarah Said – Death Cab for Cutie
...
📁 Project Structure
arduino
Copy
Edit
.
├── Emotion_aware_music_system.ipynb
├── emotion_map.py             # emotion → genre logic
├── moodbot.py                 # main entrypoint
├── utils/
│   ├── spotify_helpers.py     # search, fallback, formatting
│   └── emotion_classifiers.py # text classification pipelines
└── README.md
✨ Future Upgrades
Add GUI with Streamlit or Gradio

User history → persistent personalized playlists

Swap in newer zero-shot models (e.g., Mixtral or InstructorXL)

Emotion clustering over time

🤖 Models Used
boltuix/bert-emotion

valhalla/distilbart-mnli-12-3 (zero-shot)

spotipy (Spotify client)

Optional: gliclass pipeline imported (not active yet)

❤️ Why This?
Because emotion is messy, and playlists shouldn’t be.
This project helps music meet you where you are—not where the algorithm thinks you should be.