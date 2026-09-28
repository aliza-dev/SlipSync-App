# SlipSync: Automated Financial Reconciliation and Notification App

## Project Abstract
SlipSync is a mobile application built to automate how small B2B businesses track and verify their offline bank deposits. The workflow starts the moment a user snaps a photo of a physical deposit slip using their phone. Instead of relying on manual data entry, the system uses an AI Vision model to accurately extract the transaction ID, date, and deposited amount. 

To make the system reliable for real financial use, the backend is engineered to handle race conditions and enforce strict idempotency—ensuring a slip is never processed twice by mistake. Once the data is verified, it updates a PostgreSQL ledger. Finally, a background job pushes this update to a messaging queue, which automatically fires off a WhatsApp notification with the payment proof to the supplier. The core focus is on backend resilience, ensuring the AI extraction, database writes, and messaging integrations work flawlessly together on the go.
