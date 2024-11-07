# ITWLAB2
# Attach the body to the email
msg.attach(MIMEText(body, 'plain'))

# Sending the email
try:
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login(sender_email, password)
    server.send_message(msg)
    print("Email sent successfully!")
except Exception as e:
    print(f"Failed to send email: {e}")
finally:
    server.quit()
