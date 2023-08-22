# DJ Viral
📂 Database DJ Viral by [Gakkari](https://t.me/Gakkari)

## ```Module```
node-fetch or axios

## ```Example on the WhatsApp bot```
```
case 'djviral': {
    try {
        let response = await fetch('https://raw.githubusercontent.com/BotzIky/DJ-Viral/main/database.json');
        let data = await response.json();
        let randomIndex = Math.floor(Math.random() * data.results.length);
        let randomResult = data.results[randomIndex];
        let downloadLink = randomResult.download;
        let thumbnail = randomResult.thumbnail;
        let caption = `
▸ Tittle: ${randomResult.title}
▸ Channel: ${randomResult.channel}
▸ YouTube Link: ${randomResult.link}
▸ Size: ${randomResult.size}
        `;
        const djviral = await client.sendMessage(from, { image: { url: thumbnail }, caption: caption }, { quoted: m });
        await client.sendMessage(from, { audio: { url: downloadLink }, mimetype: 'audio/mp4', fileName: `${randomResult.title}.mp4` }, { quoted: djviral });
    } catch (error) {
        console.error(error);
        m.reply('An error occurred while fetching and sending the audio.');
    }
}
break;
```
