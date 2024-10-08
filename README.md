# FCM HTTP v1 Notification Sender

This project demonstrates how to send notifications to Android and iOS devices using the Firebase Cloud Messaging (FCM) HTTP v1 API. It generates OAuth2 access tokens using a service account and sends notifications to a device using the FCM token.

## Prerequisites

Before running the project, ensure you have the following:

1. **Firebase Project**: You must have a Firebase project created and set up for FCM.
2. **Service Account JSON File**: Download the service account credentials from Firebase Console.
3. **FCM Token**: The target device must have an FCM token generated by the Firebase SDK.


### OPTION 1 : Clone and Run in Your System

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/ksaurabh4/fcm-http-v1-notification-sender.git
    cd fcm-http-v1-notification-sender
    ```

2. Install the required Python packages:

    ```bash
    pip install google-auth requests
    ```

## Configuration

1. **Service Account Setup**:

    - You can provide the path to your service account JSON file or paste its content directly into the code.

    Option 1: Provide the file path of your service account JSON:
    
    ```python
    SERVICE_ACCOUNT_FILE = './path_to_your_serviceAccountKey.json'
    ```

    Option 2: Paste the JSON content directly into `SERVICE_ACCOUNT_INFO` in the code:

    ```python
    SERVICE_ACCOUNT_INFO = {
      "type": "",
      "project_id": "",
      "private_key_id": "",
      "private_key": "",
      "client_email": "",
      "client_id": "",
      "auth_uri": "",
      "token_uri": "",
      "auth_provider_x509_cert_url": "",
      "client_x509_cert_url": "",
      "universe_domain": ""
    }
    ```

2. **Firebase Project ID**:

    Set your Firebase project ID in the `PROJECT_ID` variable:

    ```python
    PROJECT_ID = "your-project-id"
    ```

3. **Target Device FCM Token**:

    Set the target device's FCM token in the `TARGET_FCM_TOKEN` variable:

    ```python
    TARGET_FCM_TOKEN = "your-device-fcm-token"
    ```

4. **Notification Details**:

    Customize the notification title and body by modifying the `NOTIFICATION_TITLE` and `NOTIFICATION_BODY` variables:

    ```python
    NOTIFICATION_TITLE = 'Your Notification Title'
    NOTIFICATION_BODY = 'Your notification body message.'
    ```

## Usage

### Run Locally

1. Run the Python script to send a notification:

    ```bash
    python fcm_sender.py
    ```

2. Upon successful execution, the script will send a notification to the target device and display the response in the console.

### OPTION 2 : Run on Google Colab Directly

You can also run this script directly in Google Colab by uploading your service account key and running the code. To do so:

1. Open Google Colab by clicking [here](https://colab.research.google.com/).
2. Upload your service account JSON file to Colab.
3. Update the `SERVICE_ACCOUNT_FILE` path or paste the JSON content as per the instructions above.
4. Run the code to send the notification.

If you'd prefer to use the pre-existing Colab notebook, you can [click here to open the notebook]([https://colab.research.google.com/drive/1-lxmNV8_j7CabMejA8QAkFrjJ4GSurdx](https://colab.research.google.com/drive/1AC3iyBmIusHrXayNy5XIf6BiK3QWlPv_)).

Colab is a convenient cloud-based environment that doesn't require local setup, making it easy to experiment and run Python scripts from anywhere.

## Customizing the Message Payload

If you want to include a custom data payload along with the notification, you can add it to the `message` dictionary:

```python
message = {
    "message": {
        "token": token,
        "notification": {
            "title": title,
            "body": body
        },
        "data": {
            "key1": "value1",
            "key2": "value2"
        }
    }
}
```

## Error Handling
In case of issues with sending the message or generating the access token, appropriate error messages will be printed to the console, detailing the cause of failure.

## License
This project is licensed under the MIT License. See the [LICENSE file](https://github.com/ksaurabh4/fcm-http-v1-notification-sender/blob/main/LICENSE) for details.
