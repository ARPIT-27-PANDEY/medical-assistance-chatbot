# 🩺 Medical Assistance Chatbot

An AI-assisted **medical information chatbot** designed to provide users with accessible information related to medicines, their composition, uses, side effects, manufacturers, and related details.

The project is centered around a structured medicine database, `Medicine_Details.csv`, which contains information about a large collection of medicines. The repository also includes a sample audio response demonstrating the conversational/voice-response aspect of the project.

> ⚠️ **Disclaimer:** This project is intended for educational and demonstration purposes. It is **not a replacement for a qualified doctor, pharmacist, or other healthcare professional** and should not be used for medical diagnosis, treatment, or emergency decision-making.

---

## 📌 Project Overview

Accessing reliable medicine information can be difficult for users who are unfamiliar with medical terminology or do not know where to find relevant information.

The goal of this project is to provide a conversational interface through which users can obtain structured medicine-related information in an easier and more accessible way.

The core knowledge source is:

```text
Medicine_Details.csv
```

which contains medicine-related information such as:

```text
Medicine Name
Composition
Uses
Side Effects
Image URL
Manufacturer
Excellent Review %
Average Review %
Poor Review %
```

The dataset contains **11,825 medicine records** according to analyses of the same `Medicine_Details.csv` dataset structure.

---

# 🎯 Objectives

The main objectives of the project are:

- Build a conversational interface for medical-information queries.
- Provide structured information about medicines.
- Help users understand medicine composition and common uses.
- Surface listed side effects associated with medicines.
- Provide manufacturer and other available medicine metadata.
- Make medicine information easier to access through a chatbot-style interaction.
- Explore the use of conversational AI for healthcare-information applications.

---

# 🧠 Concept

The system can be viewed as a knowledge-driven medical assistance workflow:

```text
                  User Query
                      │
                      ▼
             ┌─────────────────┐
             │  Query Analysis │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Medicine        │
             │ Information     │
             │ Retrieval       │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Medicine        │
             │ Database        │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Relevant        │
             │ Information     │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Chatbot         │
             │ Response        │
             └────────┬────────┘
                      │
                      ▼
                    User
```

The repository currently provides the medicine dataset and an example response-audio file that can be used as supporting resources for the chatbot workflow.

---

# 💊 Medicine Knowledge Base

The main data source is:

```text
Medicine_Details.csv
```

The dataset contains structured information about medicines.

## Dataset Fields

| Field | Description |
|---|---|
| `Medicine Name` | Name of the medicine |
| `Composition` | Active composition/ingredients listed for the medicine |
| `Uses` | Listed medical uses |
| `Side_effects` | Listed side effects |
| `Image URL` | Image/reference URL associated with the medicine |
| `Manufacturer` | Manufacturer of the medicine |
| `Excellent Review %` | Percentage of excellent reviews |
| `Average Review %` | Percentage of average reviews |
| `Poor Review %` | Percentage of poor reviews |

The dataset structure and field names are consistent with publicly available analyses of this medicine dataset.

---

# 🔄 Example Query Flow

A user may ask a medicine-related question such as:

```text
"What is Paracetamol used for?"
```

or:

```text
"What are the side effects of this medicine?"
```

The conceptual workflow is:

```text
User Question
     │
     ▼
Identify Medicine / Query
     │
     ▼
Search Medicine Knowledge Base
     │
     ▼
Retrieve Relevant Fields
     │
     ├── Medicine Name
     ├── Composition
     ├── Uses
     ├── Side Effects
     └── Manufacturer
     │
     ▼
Generate User-Friendly Response
```

---

# 🔍 Information Provided

Depending on the medicine available in the dataset, the chatbot can be designed to provide information such as:

### Medicine Name

Identifies the medicine relevant to the query.

### Composition

Provides the listed composition or active ingredients.

### Uses

Displays the medical uses associated with the medicine in the knowledge base.

### Side Effects

Displays side effects recorded in the dataset.

### Manufacturer

Provides the listed manufacturer.

### Additional Information

The dataset also contains:

- Medicine image URLs
- Excellent review percentage
- Average review percentage
- Poor review percentage

These fields can be incorporated into an expanded chatbot interface.

---

# 🎙️ Response Audio

The repository contains:

```text
response (1).mp3
```

This file serves as a sample audio response associated with the chatbot project.

A voice-enabled version of the system can conceptually follow:

```text
              User Input
                  │
        ┌─────────┴─────────┐
        │                   │
        ▼                   ▼
      Text                Voice
        │                   │
        │             Speech Processing
        │                   │
        └─────────┬─────────┘
                  ▼
             Query Handling
                  │
                  ▼
          Medicine Information
                  │
                  ▼
             Text Response
                  │
                  ▼
          Optional Voice Output
                  │
                  ▼
                User
```

The current repository includes the response audio artifact, but does not contain the source implementation for speech recognition or text-to-speech generation.

---

# 🗃️ Repository Structure

The current repository contains:

```text
medical-assistance-chatbot/
│
├── Medicine_Details.csv
│   └── Medicine information dataset
│
├── response (1).mp3
│   └── Sample audio response
│
└── README.md
    └── Project documentation
```

The GitHub repository currently exposes these files on the `main` branch.

---

# 📊 Dataset Characteristics

The medicine dataset contains thousands of records covering different pharmaceutical products.

A publicly available analysis of the same dataset reports:

```text
Rows    : 11,825
Columns : 9
```

The dataset contains both categorical/textual fields and numerical review-percentage fields.

### Data Types

The textual fields include:

```text
Medicine Name
Composition
Uses
Side_effects
Image URL
Manufacturer
```

The review fields are numerical:

```text
Excellent Review %
Average Review %
Poor Review %
```


---

# 🧩 Possible System Architecture

A complete implementation can be organized into the following logical components:

```text
┌──────────────────────────────────────────┐
│              User Interface              │
│                                          │
│   Text Query / Optional Voice Input      │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│             Query Processing             │
│                                          │
│  Medicine Name / Intent Identification   │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│           Medicine Knowledge Base        │
│                                          │
│          Medicine_Details.csv            │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│         Relevant Information Retrieval   │
│                                          │
│  Composition / Uses / Side Effects /     │
│  Manufacturer / Reviews / Image          │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│           Response Generation            │
└────────────────────┬─────────────────────┘
                     │
              ┌──────┴──────┐
              │             │
              ▼             ▼
          Text Output    Audio Output
                            │
                            ▼
                     response (1).mp3
```

---

# 🛠️ Technology Concepts

The repository is centered around the following technical concepts:

- **Conversational AI**
- **Natural Language Processing**
- **Structured medical knowledge retrieval**
- **CSV-based knowledge representation**
- **Medicine information search**
- **Voice-response support**

Because the current public repository does not include the chatbot source files or a dependency specification, the exact framework, language-model provider, NLP library, or voice-processing library used in the original implementation cannot be verified from the repository itself.

---

# 🚀 Getting Started

## Prerequisites

For working with the dataset, a basic Python environment is sufficient.

Recommended environment:

```text
Python 3.8+
```

Common data-analysis packages that can be used with the dataset include:

```bash
pip install pandas numpy
```

> These packages are sufficient for inspecting and querying the CSV dataset, but the repository does not currently provide a `requirements.txt` specifying the original chatbot environment.

---

# 📥 Clone the Repository

```bash
git clone https://github.com/ARPIT-27-PANDEY/medical-assistance-chatbot.git
```

Move into the project directory:

```bash
cd medical-assistance-chatbot
```

---

# 📖 Working with the Medicine Dataset

Load the dataset using Pandas:

```python
import pandas as pd

df = pd.read_csv("Medicine_Details.csv")

print(df.head())
print(df.shape)
print(df.columns)
```

The expected columns are:

```python
[
    "Medicine Name",
    "Composition",
    "Uses",
    "Side_effects",
    "Image URL",
    "Manufacturer",
    "Excellent Review %",
    "Average Review %",
    "Poor Review %"
]
```

---

# 🔎 Example Medicine Search

A simple exact-name search can be performed using:

```python
import pandas as pd

df = pd.read_csv("Medicine_Details.csv")

medicine_name = "Paracetamol"

result = df[
    df["Medicine Name"]
    .str.contains(medicine_name, case=False, na=False)
]

print(result)
```

---

# 💡 Example Information Retrieval

Once a medicine has been identified, relevant fields can be displayed:

```python
row = result.iloc[0]

print("Medicine:", row["Medicine Name"])
print("Composition:", row["Composition"])
print("Uses:", row["Uses"])
print("Side Effects:", row["Side_effects"])
print("Manufacturer:", row["Manufacturer"])
```

This provides the core structured information required by a medicine-information chatbot.

---

# 💬 Example Chatbot Interaction

A conceptual interaction could look like:

```text
User:
What is this medicine used for?

Assistant:
The medicine is listed in the database with the following uses:
<Uses from the medicine database>

User:
What are its side effects?

Assistant:
The listed side effects are:
<Side effects from the medicine database>
```

The chatbot can be extended to support follow-up questions by maintaining the currently selected medicine as conversation context.

---

# 🔗 Context-Aware Conversation

A useful conversational design is:

```text
User:
Tell me about Medicine X.

Assistant:
Medicine X contains <composition> and is listed for <uses>.

User:
What are its side effects?

Assistant:
The listed side effects for Medicine X are <side effects>.
```

Instead of requiring the user to repeat the medicine name, the application can maintain the medicine selected during the current conversation.

---

# 📈 Possible Extensions

The current repository can be extended into a more complete medical-assistance application by adding:

### 1. Natural Language Query Understanding

Allow users to ask questions in natural language rather than requiring an exact medicine name.

```text
"What medicine information do you have about X?"
```

### 2. Semantic Search

Use embeddings and vector search to retrieve medicines and descriptions based on meaning rather than exact string matches.

```text
User Query
    │
    ▼
Text Embedding
    │
    ▼
Vector Search
    │
    ▼
Relevant Medicine Records
```

### 3. Conversational Memory

Maintain context across multiple turns:

```text
Medicine → Current Topic → Follow-up Question
```

### 4. Voice Interaction

Extend the existing response-audio concept to support:

```text
Speech → Text → Query → Response → Speech
```

### 5. Web / Mobile Interface

Expose the chatbot through:

- Web application
- Mobile application
- Streamlit interface
- REST API

### 6. Medicine Image Support

The dataset already contains image URLs, making it possible to build interfaces that show medicine images alongside retrieved information.

---

# 🔐 Safety and Responsible Use

Medical applications require additional care compared with ordinary conversational applications.

This project should be treated as an **information retrieval and educational system**, not as an autonomous diagnostic or prescribing system.

The application should:

- Clearly communicate that responses are informational.
- Avoid presenting generated information as a confirmed diagnosis.
- Encourage consultation with qualified healthcare professionals.
- Avoid making unsupported dosage or treatment recommendations.
- Handle uncertainty explicitly.
- Avoid storing sensitive personal medical information unnecessarily.
- Use trusted and appropriately licensed medical sources for production systems.

---

# ⚠️ Medical Disclaimer

This project is for **educational and research purposes only**.

The information available through the dataset or chatbot should **not** be interpreted as medical diagnosis, professional medical advice, or a prescription.

Always consult a qualified doctor, pharmacist, or other healthcare professional before starting, stopping, or changing medication.

For medical emergencies, contact appropriate emergency medical services immediately.

---

# 📚 Dataset Reference

The `Medicine_Details.csv` file contains structured medicine information including medicine names, composition, uses, side effects, image URLs, manufacturers, and review percentages. A publicly available analysis of this dataset reports 11,825 records across 9 columns.

---

# 👨‍💻 Author

**Arpit Kumar Pandey**

Indian Institute of Technology Roorkee

GitHub:

https://github.com/ARPIT-27-PANDEY

---

# 🔗 Repository

https://github.com/ARPIT-27-PANDEY/medical-assistance-chatbot

---

# ⭐ Project Summary

```text
                 Medical Assistance Chatbot
                           │
                           ▼
                     User Query
                           │
                           ▼
                 Medicine Information
                      Retrieval
                           │
                           ▼
                Medicine_Details.csv
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
        ▼                  ▼                  ▼
   Composition           Uses           Side Effects
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                           ▼
                    User Response
                           │
                           ▼
                  Optional Voice Output
```

The project demonstrates how a structured medicine knowledge base can serve as the foundation for a conversational **medical-assistance application**, with opportunities to extend it using NLP, semantic retrieval, conversational memory, and voice interaction.
