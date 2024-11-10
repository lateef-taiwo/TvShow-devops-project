# # Build the image from python:3.10-slim-buster
# FROM python:3.10-slim-buster
# # make and change directory inside the container image to /backend-flask
# WORKDIR /backend-flask
# # Copy requirements.txt from host to container image
# COPY requirements.txt requirements.txt
# # use pip3 to install the dependencies/packages stated in requirements.txt
# RUN pip3 install -r requirements.txt
# # copy everything from the cuurent directory in the host to the current directory (/backend-flask) in the container image
# COPY . .
# # set env var
# ENV FLASK_ENV=development
# # expose port for binding 
# EXPOSE ${PORT}
# # Run this command to build the container image to run on port 4567
# #CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

# CMD [ "uvicorn", "main:app" , "--reload"]  

# Use an official Python runtime as a base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /backend-api

# Copy the requirements file into the container
COPY requirements.txt .

# Install any dependencies specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the FastAPI app code into the container
COPY . .

# Expose port 80 for the FastAPI application
EXPOSE 80

# Command to run the FastAPI application using uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]