import random
import time
from telegram import Bot

TOKEN = "YOUR_BOT_TOKEN"
CHAT_ID = "YOUR_CHAT_ID"

bot = Bot(token=TOKEN)

def generate_signal():
    # Simulated multiplier prediction
    multiplier = round(random.uniform(1.20, 5.00), 2)
    
    if multiplier < 2:
        signal = "LOW RISK ⚠️ Cash out early"
    elif 2 <= multiplier < 3:
        signal = "MEDIUM 🚀 Try 2x"
    else:
        signal = "HIGH 🚀🔥 Go above 3x"

    return multiplier, signal

def send_signal():
    multiplier, signal = generate_signal()
    message = f"🎯 Aviator Signal\n\nPredicted Multiplier: {multiplier}x\nAdvice: {signal}"
    
    bot.send_message(chat_id=CHAT_ID, text=message)

while True:
    send_signal()
    time.sleep(60)  # sends every 60 seconds# Aviator-signals
Auto signals 24/7 running 
