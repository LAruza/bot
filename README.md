import discord

# ayricaliklar (intents) değişkeni botun ayrıcalıklarını depolayacak
intents = discord.Intents.default()
# Mesajları okuma ayrıcalığını etkinleştirelim
intents.message_content = True
# client (istemci) değişkeniyle bir bot oluşturalım ve ayrıcalıkları ona aktaralım
client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print(f'We have logged in as {client.user}')

@client.event
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith('Selam'):
        await message.channel.send("As bro hoşgeldin :kaaba: ")
    elif message.content.startswith('$İklim'):
        await message.channel.send(f' {client.user} Hava Kirliliği: Atmosferde zararlı gazlar, partiküller ve kimyasalların yüksek miktarlarda bulunmasıdır. Örneğin, hava kirliliği egzoz gazları, endüstriyel emisyonlar ve yanıcı fosil yakıtların kullanımı nedeniyle oluşabilir.Su Kirliliği: Suların nehirler, göller, okyanuslar kirletilmesidir. Sanayi atıkları, tarım ilaçları, evsel atıklar, petrol sızıntıları ve diğer kimyasallar su kaynaklarına yayıldığında su kirliliği oluşur.Toprak Kirliliği: Toprakların zararlı kimyasallarla veya kirleticilerle kontamine edilmesidir. Kimyasal atıkların yeraltı sularına sızması veya kimyasalların toprakta birikmesi, toprak kirliliğine neden olur.Gürültü Kirliliği: Fazla gürültü seviyelerinin insan sağlığına veya çevreye olumsuz etkileri olduğunda meydana gelir. İnşaat faaliyetleri, trafik, fabrika gürültüsü gibi kaynaklardan kaynaklanabilir.Işık Kirliliği: Yüksek ışık seviyelerinin geceleyin çevre üzerinde yarattığı olumsuz etkilere işaret eder. Bu tür kirliliğin nedeni, aşırı aydınlatma ve ışık kaynaklarının yanlış kullanımı olabilir.Radyasyon Kirliliği: Radyoaktif maddelerin nükleer santrallerden veya nükleer kazalardan sızması sonucu ortaya çıkan bir tür kirliliktir.')


client.run("MTE2NzUxMjE2NzY1OTA4MTc1OA.G9iDTK.0h0iWeOKiI444ZMvuOIUSL9KPT005owAdmt58Y")
