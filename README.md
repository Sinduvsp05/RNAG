# Retrieval Non Augmented Generation (RNAG)

## Overview
Retrieval Non Augmented Generation (RNAG) is an innovative approach in natural language processing that refrains from conventional data augmentation methods used in many generative models. Instead, RNAG focuses on directly answering queries based solely on internal data, thus eliminating the need for incorporating external information sources like retrieval-augmented generation (RAG) techniques.

## Key Features
- **Non-Augmentation**: Unlike RAG variants that depend on data augmentation, RNAG leverages internal logical constructs to make inferences and generate responses.
- **Direct Query Handling**: The approach utilizes input queries as they are, fostering quicker response times by sidestepping complex retrieval processes.
- **Session Management**: Organizes dialogue through defined sessions, maintaining state (queries, responses) across interactions.
- **Embedding and Similarity**: Employs embedding techniques to assess similarity between queries and stored contexts, ensuring relevant responses.

## Implementation Details
The core implementation of RNAG as demonstrated in the provided code showcases handling incoming queries through various functions. Here are a few key components:

### **JsonDB Class**
Handles the storage and retrieval of queries and their corresponding responses using embeddings for similarity comparison.

### **Session Class**
Manages individual user sessions, storing conversations and handling offline queries.

### **MainProcessWorkflow Class**
Coordinates the overall workflow, managing sessions, handling queries, and processing offline queries.

### **Key Methods**
- `start_new_session`: Initializes a new session.
- `handle_query`: Processes incoming queries, retrieves or generates responses based on session data.
- `offline_cosine_similarity`: Computes similarity between queries and stored data when offline.
- `process_offline_queries`: Processes stored offline queries when back online.
- `save_session_to_json`: Saves session data to a JSON file.
- `load_session_from_json`: Loads session data from a JSON file.
- `load_all_sessions`: Loads all session data from the session folder.
- `clear_memory`: Clears unused variables to free up memory.
- `reinitialize_models`: Reinitializes models to ensure they are up-to-date.

## Setup and Installation

### **Prerequisites**
- Python 3.7+
- Hugging Face Token

### **Installation Steps**
#### 1. Clone the repository:
```bash
git clone <repository_url>
cd <repository_directory>
```
#### 2. Install the required packages:
```bash
pip install -r requirements.txt
```
#### 3. Set the Hugging Face Token:
```bash
export HUGGINGFACE_TOKEN=<your_hugging_face_token>
```
#### 4. Run the Streamlit application:
```bash
streamlit run app.py
```

## Running in Google Colab
#### **1. Install LocalTunnel:**
```bash
!npm install localtunnel
```
#### **2. Get IP Address for LocalTunnel:**
```python
import urllib
print("Password/Endpoint IP for LocalTunnel is:", urllib.request.urlopen('https://ipv4.icanhazip.com').read().decode('utf8').strip("\n"))
```
#### **3. Run Streamlit and LocalTunnel:**
```bash
!streamlit run app.py &>/content/logs.txt & npx localtunnel --port 8501
```
#### **4. Access the application:**
A link will be displayed. Click it and paste the IP address of LocalTunnel in it. Let the code run.

---
### **Contributions**
Feel free to contribute by submitting issues or creating pull requests to improve RNAG.

### **License**
This project is licensed under the MIT License.

---
🚀 **Happy Coding!**

