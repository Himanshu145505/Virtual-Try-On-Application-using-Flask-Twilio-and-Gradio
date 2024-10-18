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
- Python 3.x installed on your machine.

## Twilio Setup
1. Create a [Twilio account](https://www.twilio.com/try-twilio).
2. Activate the Twilio Sandbox for WhatsApp.
3. Get your Twilio **Account SID** and **Auth Token** from your Twilio console.
4. Take note of the Twilio Sandbox number for sending and receiving WhatsApp messages.

## Hugging Face Setup
1. Create a [Hugging Face account](https://huggingface.co/join).
2. Use the **Nymbo Virtual Try-On** model available on Hugging Face Spaces: [Nymbo Virtual Try-On](https://huggingface.co/spaces/nymbo).

## Installation
Clone the repository:
```bash
git clone https://github.com/your-username/virtual-tryon-whatsapp.git
cd virtual-tryon-whatsapp

Install the required Python packages:




