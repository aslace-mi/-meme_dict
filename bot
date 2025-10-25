import telebot
import random
from telebot.types import ReactionTypeEmoji
from telebot.types import (
    ReplyKeyboardMarkup, 
    KeyboardButton, 
    WebAppInfo,
    InlineKeyboardMarkup,
    InlineKeyboardButton
)
from bot_logic import gen_pass

bot = telebot.TeleBot("")
WEB_URL = "https://pytelegrambotminiapp.vercel.app"

@bot.message_handler(commands=['start'])
def send_welcome(message):
    bot.reply_to(message, "Привет! Я твой Telegram бот. Напиши что-нибудь!")

@bot.message_handler(commands=['hello'])
def send_hello(message):
    bot.reply_to(message, "Привет! Как дела?")

@bot.message_handler(commands=['bye'])
def send_bye(message):
    bot.reply_to(message, "Пока! Удачи!")


@bot.message_handler(func=lambda message: True)
def echo_all(message):
    if message.text == "пароль":
        bot.reply_to(message,gen_pass(10))
    elif message.text == "смайлик":
        bot.reply_to(message,  '(⁄ ⁄>⁄ ▽ ⁄<⁄ ⁄)')
    else:
        emo = ["\U0001F525", "\U0001F917", "\U0001F60E"]  # or use ["🔥", "🤗", "😎"]
        bot.set_message_reaction(message.chat.id, message.id, [ReactionTypeEmoji(random.choice(emo))], is_big=False)

@bot.message_reaction_handler(func=lambda message: True)
def get_reactions(message):
    bot.reply_to(message, f"You changed the reaction from {[r.emoji for r in message.old_reaction]} to {[r.emoji for r in message.new_reaction]}")


bot.polling()
