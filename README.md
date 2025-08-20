Smart Traffic Violation Detection System

This project was created by a team of six with the goal of solving a common real-world issue – handling traffic violations in a faster and smarter way. Usually, traffic departments rely on manual work to track and report violations, which can be slow and sometimes inaccurate. We wanted to build a system that could automatically detect violations, identify the vehicle involved, and notify the owner immediately.

What We Did

We built a web application using Python and Streamlit where an authorized person can log in and upload images of traffic violations. Once an image is uploaded, the system takes care of everything else.

The flow works like this:

Login – The user logs in securely through AWS Cognito.

Upload Image – The violation photo is uploaded to the app.

Violation Detection – The system uses AWS Bedrock to analyze the image and understand the type of violation (for example, no helmet, triple riding, or signal jump).

License Plate Reading – OCR is applied on the image to detect the vehicle’s license plate number.

Owner Lookup – The license plate number is matched with the vehicle owner’s details stored in DynamoDB, which includes the owner’s name, phone number, and email.

Notification – Once the match is found, an email is sent automatically to the vehicle owner using SMTP, with the details of the violation and the fine information.

So the whole process goes from uploading the picture to directly notifying the owner in just a few seconds.

My Role

I took the lead role in this project. My main responsibilities were on the backend and AWS integration side. I connected AWS services like Rekognition, Bedrock, and DynamoDB together so the system could actually understand the image and update the database. I also implemented the login system using Cognito, wrote the logic to handle license plate detection, and made sure email notifications were sent properly through SMTP.

Besides coding, I also guided the team, broke down tasks for each member, and helped debug when services were not connecting correctly. I worked a lot on IAM permissions too, because AWS services need to talk to each other securely, and that setup was tricky.

Challenges We Faced

Like any real project, this one also came with challenges. Sometimes OCR was not accurate when the license plate was blurred, so we had to improve how images were processed. We also faced delays when AWS services had to handle bigger images. IAM permissions were another problem – if not set correctly, one service could not access another, so we had to carefully configure roles and policies. We also worked on making sure the emails sent through SMTP were not landing in the spam folder, which took some extra effort.

Why It Matters

This project can be very useful for traffic departments and even private organizations. It reduces manual work, avoids errors, and makes sure owners are notified quickly. It also helps create more responsible drivers since they know violations are being tracked and reported automatically.
