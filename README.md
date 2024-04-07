# Bulky-sms-2
from twilio.rest import Client

def send_sms(account_sid, auth_token, from_number, to_number, message_body):
    """
    Sends an SMS using Twilio API.

    :param account_sid: Twilio Account SID
    :param auth_token: Twilio Auth Token
    :param from_number: Twilio phone number sending the message
    :param to_number: Recipient's phone number
    :param message_body: Body of the SMS message
    """
    try:
        # Initialize Twilio client
        client = Client(account_sid, auth_token)

        # Send the message
        message = client.messages.create(
            body=message_body,
            from_=from_number,
            to=to_number
        )

        print("Message sent successfully to", to_number)
    except Exception as e:
        print("Error:", e)

# Twilio credentials
account_sid = 'your_account_sid'
auth_token = 'your_auth_token'

# Twilio phone number
from_number = '7987882931'

# Recipient's phone number (your contact number)
to_number = '7987882931'

# Message content
message_body = 'CG BSC Nursing , PPHT प्रवेश परीक्षा के लिए निःशुल्क डेमो क्लास  10 अप्रैल तक
💥 फिजिक्स, बायलॉजी,केमिस्ट्री ,
💥11वी व 12 वी 
💥क्लास का समय 12.30 से 5 बजे तक
💥 2 महीने का क्रैश कोर्स.'

# Send the SMS
send_sms(कैरियर कोचिंग एकेडमी चारामा from_number, to_number, message_body)
