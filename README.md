# Virtual-Try-On-Application-using-Flask-Twilio-and-Gradio
This repository contains the code for a virtual try-on application built using Flask, Twilio's WhatsApp API, and Gradio's virtual try-on model. Users can send images via WhatsApp to try on garments virtually, and the results are sent back to them.

## Features
- Receive images of a person and a garment via WhatsApp.
- Use Gradio’s API to generate virtual try-on results.
- Return the result image to the user via WhatsApp.
- Uses Twilio Sandbox for WhatsApp for easy prototyping and testing.

## Technologies Used
- **Flask**: Backend server to handle requests and interact with Twilio and Gradio.
- **Twilio API**: To send and receive WhatsApp messages and media.
- **Gradio**: For interacting with the virtual try-on model.
- **Ngrok**: For exposing the local server to the internet for WhatsApp interaction.
- **OpenCV**: For handling images.

## Prerequisites
Before running this project, ensure you have the following:
- Twilio account with WhatsApp sandbox setup.
- Hugging Face account to use the Gradio API.
- Python 3.6+ installed on your machine.

## Twilio Setup
1. Create a [Twilio account](https://www.twilio.com/try-twilio).
2. Activate the Twilio Sandbox for WhatsApp.
3. Get your Twilio **Account SID** and **Auth Token** from your Twilio console.
4. Take note of the Twilio Sandbox number for sending and receiving WhatsApp messages.

## Hugging Face Setup
1. Create a [Hugging Face account](https://huggingface.co/join).
2. Use the **Nymbo Virtual Try-On** model as API available on Hugging Face Spaces: [Nymbo Virtual Try-On](https://huggingface.co/spaces/Nymbo/Virtual-Try-On).

## Installation
Clone the repository:
```bash
git clone https://github.com/your-username/virtual-tryon-whatsapp.git
cd virtual-tryon-whatsapp
```
Install the required Python packages:
```
pip install -r requirements.txt
```
Set up your environment variables:
```
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
```

### Running the Application
Start the Flask server:
```
python app.py
```
Start ngrok on port 8080:
```
.\ngrok http 8080
```
Copy the ngrok forwarding URL (e.g., https://e3e3-xxxx.ngrok-free.app) and set this as your Twilio webhook under the WhatsApp Sandbox Settings:
```
https://your-ngrok-url/webhook
```
Use WhatsApp to send a message or an image to the Twilio Sandbox number, and the application will respond with the virtual try-on result.

### Code Explanation
- **app.py**: The main Flask application that handles incoming WhatsApp messages, downloads the images from Twilio, and interacts with Gradio's virtual try-on model.
- **static**: This folder stores the images temporarily that are sent by users.
- **requirements.txt**: List of dependencies required for the project.

### Key Functions
- **webhook()**: Handles incoming POST requests from Twilio, manages the session, and interacts with the Gradio API.
- **send_to_gradio()**: Sends the person and garment images to Gradio's model for processing.
- **download_image()**: Downloads media files from Twilio's API and stores them locally.

### Usage
1. Send a photo of yourself via WhatsApp to the Twilio Sandbox number.
2. You'll receive a prompt asking you to send a photo of the garment.
3. After sending the garment photo, the system will process the images and send you the result with the garment virtually applied to your photo.

## Future Enhancements
- Integrate more detailed error handling for the Gradio API.
- Add functionality to handle multiple garments or different garment categories (e.g. bottoms, shoes).
- Deploy on a production-grade WSGI server like Gunicorn instead of the Flask development server.

## License
This project is licensed under the MIT License.
   





