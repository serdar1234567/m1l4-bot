import discord
import random
import os
from discord.ext import commands

from fonksiyon import *

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} olarak giriş yaptık')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Merhaba {bot.user}! Ben bir botum!')

@bot.command()
async def heh(ctx, count_heh = 5):
    await ctx.send("he" * count_heh)

@bot.command()
async def para(ctx):
    await ctx.send(yazi_tura())

@bot.command()
async def emoji(ctx):
    await ctx.send(emoji_olusturucu())

@bot.command()
async def sifre(ctx, sifre_uzunlugu = 15):
    await ctx.send(gen_pass(sifre_uzunlugu))

@bot.command()
async def rastgelesayi(ctx, random1 = 10):
    await ctx.send(random.randint(1, random1))

@bot.command()
async def rock(ctx):
    await ctx.send("i choosed paper, i won")
@bot.command()
async def paper(ctx):
    await ctx.send("i choosed scissors, i won")
@bot.command()
async def scissors(ctx):
    await ctx.send("i choosed rock, i won")

@bot.command()
async def resimkoy(ctx):
    with open('bot\images\pythonresmi.png', 'rb') as f:
        # Dönüştürülen Discord kütüphane dosyasını bu değişkende saklayalım!
        picture = discord.File(f)
   # Daha sonra bu dosyayı bir parametre olarak gönderebiliriz!
    await ctx.send(file=picture)

@bot.command()
async def randomresim(ctx):
    resimler = os.listdir('bot\images')
    resim = random.choice(resimler)

    # Dosya adını bir değişkenden bu şekilde değiştirebilirsiniz!
    with open(f'bot\images/{resim}', 'rb') as f:
            picture = discord.File(f)
    
   # Daha sonra bu dosyayı bir parametre olarak gönderebiliriz!
    await ctx.send(file=picture)

oneriler = ['nasa benim hedef kitlem. uzaydaki çöpler benim sorunum. uzay mekikleri arasına balık ağı dizilir. daha sonra çöpler toplanır ve mekiklerle dünyaya indirilir. Bu sayede çok fazla miktarda bir geri dönüşüm sağladık.' ,
            'turmepa benim hedef kitlem.tuzlu suyun tatlı suya çevirme. bütün dünyadaki arıtma makinelerini birleştirip mega arıtma makinesi yapıp tuzlu suyun yüzde 50sini tatlı suya çevirmek.kalan balıkları da yeriz.'
]

@bot.command()
async def banafikirver(ctx):
    await ctx.send(random.choice(oneriler))

@bot.command()
async def copy(ctx, copying = "hello"):
    await ctx.send(copying)


bot.run("token")
