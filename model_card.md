# 🎧 Model Card: Music Recommender Simulation

## 1. Model Name  

Give your model a short, descriptive name.  
Example: **VibeFinder 1.0**  

VibeBizz

---

## 2. Intended Use  

Describe what your recommender is designed to do and who it is for. 

Prompts:  

- What kind of recommendations does it generate  
- What assumptions does it make about the user  
- Is this for real users or classroom exploration  


This recommender generates music recommendations based on user preferences such as genre, mood, and energy level. It is designed for classroom exploration and testing music recommendation logic rather than for real-world deployment. The system assumes that users can provide their preferred genre, mood, and energy level.

---

## 3. How the Model Works  

Explain your scoring approach in simple language.  

Prompts:  

- What features of each song are used (genre, energy, mood, etc.)  
- What user preferences are considered  
- How does the model turn those into a score  
- What changes did you make from the starter logic  

Avoid code here. Pretend you are explaining the idea to a friend who does not program.

The model assigns a score to each song based on how closely it matches the user’s preferences. It looks at features like genre, mood, and energy. Each song receives points for matching the preferred genre, additional points for mood match, and a score based on how close its energy is to the user’s target energy. The top-scoring songs are recommended. During testing, we experimented with increasing the weight of energy to see how it affects rankings.

---

## 4. Data  

Describe the dataset the model uses.  

Prompts:  

- How many songs are in the catalog  
- What genres or moods are represented  
- Did you add or remove data  
- Are there parts of musical taste missing in the dataset  

The dataset contains 18 songs with various genres, including pop, rock, lofi, jazz, classical, synthwave, and ambient. Moods include happy, chill, intense, relaxed, focused, energetic, and more. Some genres like rock and classical are underrepresented, which may limit recommendation diversity. No songs were added or removed for these tests.
---

## 5. Strengths  

Where does your system seem to work well  

Prompts:  

- User types for which it gives reasonable results  
- Any patterns you think your scoring captures correctly  
- Cases where the recommendations matched your intuition  

Works well for users who specify high-energy preferences; top songs generally match both energy and genre.
Captures simple patterns correctly, such as ranking pop songs higher for pop-preferring users.
Recommendations often align with intuition for profiles like "Deep Intense Rock" or "High-Energy Pop."

---

## 6. Limitations and Bias 

Where the system struggles or behaves unfairly. 

Prompts:  

- Features it does not consider  
- Genres or moods that are underrepresented  
- Cases where the system overfits to one preference  
- Ways the scoring might unintentionally favor some users  

Small dataset means some genres (e.g., rock, classical) are underrepresented.
High-energy songs dominate recommendations due to heavier weighting in scoring.
Some songs repeatedly appear at the top across different profiles, creating a filter bubble.
Mood matching has less impact when energy dominates scoring.

---

## 7. Evaluation  

How you checked whether the recommender behaved as expected. 

Prompts:  

- Which user profiles you tested  
- What you looked for in the recommendations  
- What surprised you  
- Any simple tests or comparisons you ran  

No need for numeric metrics unless you created some.

Recommendations generally favored songs matching both genre and energy.
"Gym Hero" appeared at the top for multiple profiles, showing energy influence dominates mood.
Doubling the energy weight caused top songs to rank higher in score, confirming system sensitivity.
Removing or reducing mood checks can change rankings significantly.

---

## 8. Future Work  

Ideas for how you would improve the model next.  

Prompts:  

- Additional features or preferences  
- Better ways to explain recommendations  
- Improving diversity among the top results  
- Handling more complex user tastes  

Add more songs to cover underrepresented genres and moods.
Introduce more user preference features like tempo, danceability, or valence.
Improve explanation logic to clearly show why each song was ranked highly.

---

## 9. Personal Reflection  

A few sentences about your experience.  

Prompts:  

- What you learned about recommender systems  
- Something unexpected or interesting you discovered  
- How this changed the way you think about music recommendation apps  

I learned how recommender systems balance multiple features to rank items. It was interesting to see how small changes in scoring weights dramatically affect rankings. Testing different user profiles helped me understand potential biases, like high-energy songs dominating, and showed how important dataset diversity is.

## Personal refection from course portal questions

What was your biggest learning moment during this project?
How did using AI tools help you, and when did you need to double-check them?
What surprised you about how simple algorithms can still "feel" like recommendations?
What would you try next if you extended this project?

Working on the project provided valuable insights into the engineering of recommender systems. A key takeaway was the effectiveness of a simple scoring algorithm that combines genre, mood, and energy, particularly when weights are finely tuned. Utilizing AI tools like Copilot expedited the coding process but necessitated careful review of outputs for accuracy. Surprisingly, even with a small dataset, the system produced reasonable recommendations, demonstrating the power of scoring intuition over complex models. Future extensions could incorporate features like tempo and valence to enhance diversity in recommendations, addressing bias and catering to varied user preferences.