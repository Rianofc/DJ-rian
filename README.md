# DJ Viral
📁 Database DJ Viral
By [Gakkari](https://t.me/Gakkari)

# ```Needed```
## NodeJS
## Axios Module
Install the Axios module by running the following command:
- Using npm:
```
npm install axios
```
- Using yarn:
```
yarn add axios
```
Or use add this to your dependencies package.json
```
"axios": "^0.24.0",
```
## ```Example Using```
This is just an example of how to get the audio using the axios module and the NodeJS System.
```
try {
    const response = await axios.get('https://raw.githubusercontent.com/BotzIky/DJ-Viral/main/database.json');
    if (response.status === 200 && response.data && response.data.results && response.data.results.length > 0) {
      const randomIndex = Math.floor(Math.random() * response.data.results.length);
      const randomResult = response.data.results[randomIndex];
      const downloadLink = randomResult.download;
      const title = randomResult.title;
      const channel = randomResult.channel;
      const link = randomResult.link;
      const size = randomResult.size;
      await ctx.replyWithAudio({ url: downloadLink }, { caption: `Judul: ${title}\nChannel: ${channel}\nSize: ${size}\nLink: ${link}` });
    } else {
      ctx.reply('Tidak dapat mengambil data audio dari API.');
    }
  } catch (error) {
    console.error('Error:', error);
    ctx.reply('Terjadi kesalahan saat memproses perintah.');
  }
```
Information: 
This is the url to fetch data from database.json
```
const response = await axios.get('https://raw.githubusercontent.com/BotzIky/DJ-Viral/main/database.json');
```
Use the client that you are using and use the retrieval logic according to the NodeJS system that you created.
```
await ctx.replyWithAudio({ url: downloadLink }, { caption: `Tittle: ${title}\nChannel: ${channel}\nSize: ${size}\nLink: ${link}` });
```
## ```Questions and Suggestions```
Join Group Telegram: [BotzAku Group](https://t.me/Botz_Aku)
