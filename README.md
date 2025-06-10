# Chat-bot-demo

Work flow

Purpose:  To build a smart chatbot that answers basic legal queries and guides users through Indian legal procedures using natural conversation

How It Works – Step-by-Step 

Step 1:User Inputs a Question
      
      The user types something like "How To File an FIR?" using  web-based chat interface.


Step 2:  Preprocessing the Query

    2.1 Lowercasing
     Converts all characters in the user’s query to lowercase.
     Helps standardize text and avoid confusion between "FIR" and "fir".
     Example: "How To File an FIR?" → "how to file an fir?"


    2.2 Punctuation Removal
     Removes symbols like commas, question marks, and periods that don't affect intent.
     This avoids noise in the data and makes tokenization cleaner.
     Example: "how to file an fir?" → "how to file an fir"


    2.3 Tokenization
      Splits the sentence into individual words or tokens.
      These tokens are used by the model to understand sentence structure and meaning.
      Example: "how to file an fir" → [‘how’, ‘to’, ‘file’, ‘an’, ‘fir’]


    2.4 Stopword Removal 
      Removes common but low-value words like “the”, “is”, “an”, etc., which don’t add much meaning.
      Helps models focus on important words like “FIR”, “file”, “withdraw”.
      Example: [‘how’, ‘to’, ‘file’, ‘an’, ‘fir’] → [‘file’, ‘fir’]

Step 3: - Intent Classification (Main Topic Detection)
      
      The ML model (e.g., SVM or Naïve Bayes) analyzes the processed text and predicts the broad intent category like FIR, Bail, or Cybercrime.
      In short it will categorize the query with the best possible matched category.

Step 4: - Semantic Matching (Sub-intent Identification)

      Inside the predicted category (e.g., "FIR"), there can be many sub queries having same words FIR but different meaning.
      Example : "How to file FIR?" & "How to withdraw the FIR" both are in same category but different meaning.

      So in this step we will matches the query to the most similar pattern from existing training data, like:
      "How can I withdraw an FIR?" → matched with sub-intent "fir_withdrawal" 

Step 5: - Response Retrieval

      Once the correct sub-intent is identified, the chatbot fetches a predefined response from database.

Step 6: - Reply Delivered to User

      The chatbot displays the response via React-based UI. It feels like a real conversation, tailored to the user’s query.


🔧 Future Improvements:

     - Data Storage: Upgrade from static intents.json to real-time database (like MongoDB)

     - Multilingual Support: Add translation for Hindi or regional languages using Google APIs

     - Voice Input: Integrate Speech-to-Text so users can talk to the chatbot

     - AI-based Fallbacks: Connect to GPT models for dynamically generating answers when no match is found

    - Integrate the chatbot with websites and mobile apps, making legal assistance accessible through web portals and smartphone applications.



