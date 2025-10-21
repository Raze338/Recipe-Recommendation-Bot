# Recipe Recommendation Bot

An AI-powered recipe recommendation web app that suggests complete recipes—including ingredients, instructions, and nutritional breakdown—based on user-provided ingredients.  
The system uses a **fine-tuned GPT-2 model** trained on a Kaggle recipe dataset and integrates the **Nutritionix API** for macronutrient analysis.

---

## Features

- **AI-Generated Recipes** — Uses GPT-2 to generate recipe titles, ingredient lists, and step-by-step instructions.  
- **Ingredient-Based Suggestions** — Users input ingredients like “rice, tomato, beef,” and receive tailored recipes.  
- **Nutritionix API Integration** — Real-time macronutrient analysis (calories, protein, carbs, fats).  
- **Flask Web App** — Clean and lightweight UI built for quick interactions.  
- **Docker-Ready** — Easily deployable for development or production.

---

## Tech Stack

- **Languages & Frameworks:** Python, Flask  
- **Machine Learning:** GPT-2 (Hugging Face Transformers)  
- **API:** [Nutritionix](https://developer.nutritionix.com/)  
- **Frontend:** HTML, CSS, JavaScript  
- **Deployment:** Docker (optional)

---

## Project Structure

**recipe-recommendation-bot/
│
├── model/ # Fine-tuned GPT-2 model & tokenizer
├── app/
│ ├── app.py # Flask backend
│ ├── templates/ # HTML files
│ └── static/ # CSS / JS files
│
├── data/
│ └── recipes_dataset.csv # Kaggle dataset (not included in repo)
│
├── notebooks/ # Training & testing notebooks
│ └── training.ipynb
│
├── requirements.txt
├── Dockerfile
└── README.md**

---

## ⚙️ Installation

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/recipe-recommendation-bot.git
cd recipe-recommendation-bot
```

### 2. Create a virtual environment and install dependencies
python -m venv venv
source venv/bin/activate        # or venv\Scripts\activate on Windows
pip install -r requirements.txt

### 3. Set up your Nutritionix API key
Create a .env file in the root directory:
```bash
NUTRITIONIX_APP_ID=your_app_id
NUTRITIONIX_API_KEY=your_api_key
```
### 4. Run the Flask app
```bash
python app/app.py
```
Then open your browser at http://localhost:5000.

### Model Training (Optional)
If you want to fine-tune GPT-2 yourself:

Download the Kaggle recipes dataset.
Run notebooks/training.ipynb to fine-tune GPT-2.
Save the model and tokenizer in ./model/.

### Example Output
# User input:

chicken, rice, lemon

# Generated Recipe
Title: Lemon Chicken Rice Bowl

Ingredients: 
- 2 chicken breasts
- 1 cup rice
- 1 lemon
- Olive oil, garlic, salt, pepper

Instructions:
1. Cook rice until fluffy.
2. Sear chicken breasts with garlic and lemon.
3. Combine and serve with fresh lemon juice.

Nutrition:

Calories: 520 kcal
Protein: 45g
Carbs: 42g
Fats: 17g

### Docker Deployment

```bash
docker build -t recipe-bot .
docker run -d -p 5000:5000 recipe-bot
```
### Future Improvements

- Add user authentication & saved recipes
- Support for multiple cuisines and dietary restrictions
- Deploy on cloud (e.g., Render, AWS, or Azure)

