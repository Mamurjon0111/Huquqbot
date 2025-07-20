# Huquqbot import telebot

API_TOKEN = '8059313518:AAEGzdRzIB8IlpiIC4mh4aQPu0Y-uluwWic'  

bot = telebot.TeleBot(API_TOKEN)

@bot.message_handler(commands=['start', 'help'])
def send_welcome(message):
    bot.reply_to(message, "Assalomu alaykum! Men huquqiy yordamchi botman. Savolingizni yozing:")

@bot.message_handler(func=lambda message: True)
def echo_all(message):
    javob = f"Savolingiz: {message.text}\n\n(Tez orada huquqiy javoblar bilan to‘ldiramiz!)"
    bot.reply_to(message, javob)

bot.infinity_polling()
