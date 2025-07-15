# GADA GUIDE

**Emotion-Aware Health & Wellness Companion for Tourists and Hospitality in Oromia**
---

##  Overview

**GADA GUIDE** is an inclusive, offline-capable, AI-powered mobile health assistant designed to support the emotional and physical well-being of tourists especially the elderly, disabled, and illiterate traveling through Oromia. It uses TinyML, emotion recognition, and culturally intelligent guidance to ensure a safe, stress-free, and inclusive experience.
---
##  Problem Statement
Tourists often face:
- Emotional stress in unfamiliar environments
- Lack of accessible health and communication tools
- No inclusive, offline health support for travel
- Barriers for disabled, elderly, or illiterate visitors

##  Solution: GADA GUIDE

A mobile wellness assistant that:

- Detects **stress, fatigue, or illness** using AI (facial emotion, voice tone, breath)
- Provides **offline support** using **TinyML** (no internet required)
- Features **symbol-based & voice UI** for non-readers or disabled users
- Offers **multilingual guidance**, cultural etiquette tips, and emergency alerts
- Builds a **real-time wellness heatmap** for safe tourism zones
##  Project Features and Status
* Emotion detection partially done
* Offline AI health assistant progress
* Multilingual (Afaan Oromo, Amharic, English) In progress
* Symbol/Voice UI for illiterate users Prototyped 
* Emergency alerts (SOS + cultural first aid) Planned 
* Culturally aware tourist tips planned
* Proposal document completed and submitted
* UI prototype in Afaan Oromo ,Amharic and English started
* Emotion detection model – started  for offline MVP
* Firebase integration – done 
* demo is ready
* dashboard done
* user login done
* The Firebase and SQLite databases are set up and initialized correctly
* Basic emotion detection functionality is implemented
* A functional GUI allows users to interact with the application easily
* Speech-to-text features are integrated but may require an internet connection for Google services
* Basic error handling is present, particularly for Firebase and translation functions
* text,voice and chatbot interactin done for demo
* The rest is on the way and everthing is possible and i am working on it
---
##  Files in This Repo

`GADA_GUIDE_Proposal.pdf`: Full proposal document submitted to Hackathon
`README.md`: Project summary and technical overview
---

##  Prior Experience

This project builds on experience gained during a previous smart traffic system (ITMS) that used Firebase, camera sensors, and AI in real-time. The same architecture will be adapted for offline-first deployment in tourism wellness.

---

## Funding Request

We are seeking **$100,000** for:
- Finalizing the MVP
- TinyML optimization
- Firebase integration
- Emergency SOS development
- UX testing in Oromia

---

##  Call to Action

We are currently looking for:
- Investors & grant opportunities
- Technical mentorship (TinyML / Emotion AI)
- Piloting partners (Ministry of Tourism, local hospitals, hotels)

---

##  Contact

- OLJITRA LIKASA NAFABAS – Founder & AI Developer  
- Email: oljelikonafo@gmail.com  
- GitHub: https://github.com/ollikasa

---

##  License

© 2025 GADA GUIDE – All rights reserved.


#Product Info Scraper (E-Commerce):




import requests
from bs4 import BeautifulSoup
import csv

url = "https://books.toscrape.com/catalogue/category/books/travel_2/index.html"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")
products = soup.find_all("article", class_="product_pod")

with open("travel_books.csv", "w", newline='', encoding='utf-8') as f:
    writer = csv.writer(f)
    writer.writerow(["Title", "Price", "Rating"])

    for product in products:
        title = product.h3.a["title"]
        price = product.find("p", class_="price_color").text
        rating = product.p["class"][1]
        writer.writerow([title, price, rating])

print(" travel_books.csv created")



#Auto-Fill Form Automation (Using Selenium):


from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()
driver.get("https://www.w3schools.com/html/html_forms.asp")

name_input = driver.find_element(By.NAME, "firstname")
last_input = driver.find_element(By.NAME, "lastname")

name_input.send_keys("John")
last_input.send_keys("Doe")

submit_btn = driver.find_element(By.XPATH, "//form[@action='/action_page.php']//input[@type='submit']")
submit_btn.click()

time.sleep(2)
driver.quit()



#Email Notification Bot (Using SMTP):

import smtplib
from email.message import EmailMessage

email = EmailMessage()
email['Subject'] = 'Scraping Done!'
email['From'] = 'oljelikonafo@gmail.com'
email['To'] = 'trafficmanager@gmail.com'
email.set_content('Your data scraping task is complete.')

with smtplib.SMTP_SSL('smtp.gmail.com', 465) as smtp:
    smtp.login('oljelikonafo@gmail.com', 'your_app_password')
    smtp.send_message(email)

print("Email sent")


