# AI-Support-Ticket-Router

A Machine learnin support ticket simulator built with Python and Gradio. It reads a customer message, predicts which team should handle it, assigns a priority, and keeps track of the ticket.

![New ticket and dashboard](media/Screenshot%202026-09-20%20174526.png)

## Features

- Classifies tickets as **Account**, **Technical**, or **Billing**
- Routes tickets to the corresponding support team
- Assigns **High** or **Normal** priority using issue-specific keyword rules
- Creates a ticket ID and timestamp
- Shows ticket history, status, and dashboard totals
- Lets users change a ticket's status to Open, In Progress, or Resolved
- Saves category corrections for later review

## Screenshots

### Ticket history

![Ticket history](media/Screenshot%202026-09-20%20174535.png)

### Flag a ticket

![Feedback form](media/Screenshot%202026-09-20%20174603.png)

## How it works

The category classifier uses TF-IDF and logistic regression. Priority is assigned separately through keyword rules, and the support team is selected from the predicted category.

The notebook evaluates the classifier on 19 held-out tickets from an initial set of 75 written examples. It reports **94.74% accuracy on that small test set**. The app's final model is then trained on all 75 examples plus 10 additional settings-related examples. The reported score does not independently evaluate that final model or predict its performance on real customer tickets.

Watch the linked video for a video demo of the UI: https://youtu.be/HIT07Yo8qes

## Run it

1. Open `model_training.ipynb(1)` in Google Colab or Jupyter.
2. Run the cells in order.
3. Open the Gradio link displayed by the final cell.
4. Enter a sample message or write your own.

If running locally, install the dependencies first:

```bash
pip install -r requirements.txt
