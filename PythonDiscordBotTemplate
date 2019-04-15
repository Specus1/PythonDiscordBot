import discord

print(discord.__version__)

client = discord.Client()
userID = ""  # make this your ID
TOKEN = ' ' #pass ur token in here
Del = ".del"
selfDel = '.sdel'   # I did this just to do some test commands, make a proper way to do commands if not u can just do what i did here
re = ".re"
loopNUM = 1;
def is_me(m):
    return m.author == client.user


@client.event
async def on_message(message):
    newID = str(message.author)
    if newID == userID: # this makes sure only u can use ur bot thats why you would assign it to ur Discord id
    
        if message.content.startswith(Del): # checks the message you type to see if it starts with, what we call the command
            newLen = len(message.content)
            if newLen > len(Del)+1:
                newMsg1 = message.content.split(' ')[1]   # this function is basically just deleting every message
                await message.delete()
                async for message in message.channel.history(limit=int(newMsg1)):
                    await message.delete()
            else:
                return 0

        elif message.content.startswith('.yik'): # this is just printing yikes as a reaction to the latest message
            channel = message.channel
            await message.delete()
            async for message in channel.history(limit=1):
                await message.add_reaction('🇾')
                await message.add_reaction('🇮')
                await message.add_reaction('🇰')
                await message.add_reaction('🇪')
                await message.add_reaction('🇸')
            else:
                return 0
        elif message.content.startswith(re):  # this is just repeating the last message 
            newLen = len(message.content)
            newMsg = message.content
            channel = message.channel
            if newLen > len(re)+1:
                newMsg1 = newMsg.split(' ')[1]
                newMsg3 = int(newMsg1)
                await message.delete()

                async for message in channel.history(limit=1):
                    RepeatMSG = message.content
                    while (newMsg3 != 0):
                        await channel.send(RepeatMSG)
                        newMsg3 = newMsg3 - 1



            else:
                return 0


        elif message.content.startswith('.yak'):  # this is typign out yikas in reactions, easy format to follow change to what you like
            channel = message.channel             # keep in mind if theres an emote that ur server doesnt have make an exception for it
            await message.delete()
            async for message in channel.history(limit=1):
                await message.add_reaction('🇾')
                await message.add_reaction('🇮')
                await message.add_reaction('🇰')
                await message.add_reaction('🇦')
                await message.add_reaction('🇸')
            else:
                return 0



        elif message.content.startswith(selfDel): # this will delete only your messages instead of everyones
                newLen = len(message.content)
                newMsg = message.content
                channel = message.channel
                if newLen > len(selfDel) + 1:
                    newMsg1 = newMsg.split(' ')[1]
                    newMsg2 = int(newMsg1)
                    print(newMsg2)
                    await message.delete()
                    async for message in channel.history(limit=20):

                        await channel.purge(limit=newMsg2, check=is_me)



                else:
                    return 0
        else:
            return 0
    else:
        return 0


client.run(TOKEN)










