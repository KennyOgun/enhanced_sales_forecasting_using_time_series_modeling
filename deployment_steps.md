Step 1: Install Dependencies
Before you begin, make sure you have:

Python (preferably 3.8+)
pip installed
Virtual environment (optional but recommended)
MLflow, FastAPI, Uvicorn, and other dependencies

Run this in your VS Code terminal:
pip install mlflow fastapi uvicorn pandas statsmodels scikit-learn matplotlib seaborn 

Step 2: Train the Model & Track with MLflow
Create a Python script named train.py and save it in your project folder.

train.py (Model Training & MLflow Tracking)

Step 3: Run MLflow & Train the Model
In VS Code terminal, navigate to your project folder and run:

# Start MLflow UI (backend store in SQLite)
mlflow ui --backend-store-uri sqlite:///mlflow.db

📌 Go to http://localhost:5000 to see MLflow tracking UI.

Now, train the model:
python train.py

After running this, you should see a new experiment in MLflow UI.

Step 4: Deploy the Trained Model with FastAPI
Now, create another Python script app.py for the FastAPI deployment.

app.py (FastAPI API for Model Deployment)

Step 5: Run FastAPI API
In VS Code terminal, run:
python app.py

✅ Now, open http://localhost:8000/docs in your browser to test the API.

Step 6: Dockerize the Project
Create a new file Dockerfile (without extension) in your project folder.

Dockerfile:
# Use an official lightweight Python image
FROM python:3.9

# Set working directory
WORKDIR /app

# Copy everything to the container
COPY . .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose port for FastAPI
EXPOSE 8000

# Command to run the FastAPI app
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]



Step 7: Create a requirements.txt File
Inside your project folder, create requirements.txt and add:
mlflow
fastapi
uvicorn
pandas
statsmodels
scikit-learn
matplotlib
seaborn
pickle5


Step 8: Build and Run the Docker Container
Run these commands in VS Code terminal:

# Build Docker image
docker build -t video-game-forecast .

# Run container
docker run -p 8000:8000 video-game-forecast

✅ Your FastAPI service is now running inside Docker!



Final Steps: Accessing Everything
Component	       |Command	                                                        |   URL
MLflow           | UI	mlflow ui --backend-store-uri sqlite:///mlflow.db	          | http://localhost:5000
Train Model      |	python train.py	
FastAPI Docs     | 	python app.py OR docker run -p 8000:8000 video-game-forecast	| http://localhost:8000/docs
