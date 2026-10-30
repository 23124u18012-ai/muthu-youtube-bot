# Muthu YouTube Telegram Bot — Render

## Deploy
1. Upload these files to a GitHub repository: `bot.py`, `requirements.txt`, `Dockerfile`, and `render.yaml`.
2. In Render, choose **New > Blueprint** and connect that repository, or create a **Background Worker** using the Docker runtime and `Dockerfile`.
3. Add the environment variable `BOT_TOKEN` with the token from @BotFather. Do not put the token in GitHub or commit it to code.
4. Deploy and inspect the Render logs. The log should say `Muthu YouTube Downloader is starting...`.
5. Open the Telegram bot and send `/start`.

## Notes
- This is a polling bot, so use a Render Background Worker, not a static site.
- Background Workers may require a paid Render plan; check the current pricing shown in your Render dashboard.
- FFmpeg and Node.js are installed by the Dockerfile.
- The bot limits each resulting media file to 45 MB. Telegram API upload limits and YouTube availability still apply.
- Keep the bot token private. If exposed, revoke it with @BotFather and set a new `BOT_TOKEN` in Render.
