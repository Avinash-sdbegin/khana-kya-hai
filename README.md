# 🍛 Khana Kya Hai?

### Ranchi Hostel Mess & Allergy Planner

> A small AI-powered tool built for hostel students who want to quickly understand what they can eat from the mess menu based on their dietary restrictions.

## 🤔 Why I Built This

Hostel mess menus are usually simple, but they can become confusing when someone has a food allergy, intolerance, or a specific diet.

A friend may look at a menu and ask:

**"Aaj mess mein kya kha sakta hoon?"**

I built **Khana Kya Hai?** around that simple problem.

The idea is to take the day's hostel mess menu, a user's allergy or intolerance, dietary preference, and budget, and turn that information into a more useful meal recommendation.

## ✨ What It Does

- Takes the hostel mess menu as input
- Accepts allergies and food intolerances
- Considers dietary preference
- Considers a daily food budget
- Uses Google's Gemma open-weight model to analyze the menu
- Separates foods into avoid, verify, and suitable-looking options
- Suggests a simple low-cost alternative when needed
- Includes a safety reminder to verify ingredients with the mess

## 🧠 How It Works

```text
User
  |
  v
Mess Menu + Allergy + Diet + Budget
  |
  v
Google Gemma
  |
  v
Meal Analysis
  |
  v
Safety / Allergy Check
  |
  v
Final Recommendation
```

Gemma is used as the main language-model layer for understanding the menu and generating recommendations.

A separate Python-based checking layer is also used for explicit allergy-related keywords. This means the application does not blindly display the model's output.

## 🛠️ Tech Stack

- Python
- Google Gemma
- Google AI Studio
- Gradio
- Google Colab

## 🖥️ Demo

The prototype runs from Google Colab and launches a Gradio web interface.

### Example Input

```text
Today's Mess Menu:
Aloo Paratha, Paneer Butter Masala, Rice, Dal, Kheer

Allergy:
Milk / Dairy

Diet:
Vegetarian

Budget:
₹100
```

### Example Output

The application can identify items that may need to be avoided or verified and provide a practical alternative.

> ⚠️ The application is an AI prototype and is not medical advice. Ingredients, cooking methods, and cross-contact should always be verified with the hostel mess or food provider.

## 🔐 API Key Setup

The API key is **not stored in this repository**.

For the Colab version, the API key is stored using **Colab Secrets**.

Create a secret named:

```text
GEMMA_API_KEY
```

Then enable **Notebook access** for the secret.

## ▶️ How to Run

### 1. Open the notebook

Open:

```text
khana_kya_hai.ipynb
```

in Google Colab.

### 2. Add the API key

In Colab:

```text
Secrets → Add new secret
```

Use:

```text
GEMMA_API_KEY
```

### 3. Run the notebook

Run the cells in order.

The notebook launches a Gradio interface where you can enter:

- Mess menu
- Allergies / intolerances
- Dietary preference
- Daily budget

Then click:

```text
Analyze My Food
```

## 🧪 Testing

The prototype was tested using hostel-style menu examples involving:

- Dairy restrictions
- Peanut restrictions
- Vegetarian meals
- Cooking-method uncertainty
- Budget-based alternatives

The goal of these tests is to make the output useful while clearly separating uncertain cases that should be verified.

## 🌱 Why Open-Source AI?

The project uses Gemma as its AI layer because the challenge focuses on building with open-source AI and explaining why an open approach matters.

For this project, the model is used to interpret the natural-language context of a hostel menu and turn it into a personalized recommendation.

The project also keeps explicit keyword-based safety checks outside the model so that the application has a deterministic layer in addition to generative AI.

## 🏆 Hacktoberfest 2026

This project was built for the **Hacktoberfest Weekend Challenge: Build for a Friend**.

### Prize Category

**Best Use of Gemma**

The project uses Google's Gemma as its core AI model and explains how the open-weight model contributes to the application.

## ⚠️ Safety Note

This project is a prototype for educational and hackathon purposes.

It must **not** be treated as a medical or allergy-diagnosis system.

Food ingredients and preparation methods can vary between messes. Users should always verify ingredients, cooking medium, and possible cross-contact with the food provider.

## 🚀 Future Improvements

- Better ingredient and allergen detection
- Hostel-specific menu history
- More accurate price estimation
- Weekly meal planning
- Local/offline model support
- Personalized food preferences
- Better handling of regional Indian dishes

## 📄 License

MIT License
