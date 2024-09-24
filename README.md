## Demo

Watch the demonstration video:

[![Negotiation Chatbot Demo](https://www.loom.com/share/0ab5dc2f585941a1ab652171cfa74ba8?sid=97b6e0e5-80f0-4a53-ae99-6e351cc8020b)




Introduction

This repository provides two implementations for a negotiation API and a command-line tool, both leveraging Python to simulate a price negotiation process. You can choose the method that best suits your integration needs:

Flask API: A web API using Flask that allows you to integrate negotiation logic into your web applications.

Command-Line Tool: A script that lets you directly interact with the negotiation model via the command line.

Installation

Clone this repository:

Bash
git clone https://github.com/your-username/negotiation-api.git
Use code with caution.

Install dependencies using pip:

Bash
cd negotiation-api
pip install openai flask (for the Flask API)
Use code with caution.

API Usage (Flask)

Requirements:

An OpenAI API key (obtain from https://beta.openai.com/account/api-keys).
Configuration:

Replace the placeholder 'with your own OpenAI API key' in app.py.

(Optional) Adjust the base price (base_price), minimum price (min_price), and maximum price (max_price) defined in app.py to suit your product or service.

Running the API:

Start the Flask server:

Bash
python app.py
Use code with caution.

Send a POST request to the /negotiate endpoint with your user's desired price in JSON format:

Bash
curl -X POST http://localhost:5000/negotiate -H 'Content-Type: application/json' -d '{"user_input": 120}'
Use code with caution.

Replace 120 with the user's desired price.

Expected Response:

The API will respond with a JSON object containing the server's counteroffer:

JSON
{
    "response": "Let's agree on $130."
}
Use code with caution.

Command-Line Tool Usage

Running the Tool:

Make sure the dependencies are installed (see Installation above).

Execute the script:

Bash
python negotiate_price.py
Use code with caution.

User Interaction:

The script will prompt you for your desired price:

What is your desired price?
Enter a numerical value.

The script will then simulate a negotiation process using GPT-3 and provide counteroffers until a deal is reached or the user rejects the offers.

Example: Negotiation Flow

What is your desired price?
100
That's too low. The minimum price is: 100
120
I am offering the product for $135. The user desires $120. Generate a counteroffer that is within a reasonable negotiation range, considering the user's desired price and the product's value.
I can offer it for: $125
(accept or reject)
accept
Deal accepted! The price is: 125
Integration Considerations

For the Flask API, you can integrate it into your web applications to handle user input and provide negotiation responses.
The command-line tool offers a basic interactive experience but is not suitable for direct production use. You might consider integrating its negotiation logic into a more suitable application.
Further Enhancements

You could extend the API to handle different negotiation strategies beyond the basic price-based approach.
Explore other GPT-3 models or fine-tune the current model for more sophisticated negotiation tactics.
Implement error handling and validation for user input in both the API and command-line tool.
