# FileFlux – Discord File Converter Bot

[![Top.gg Verified](https://img.shields.io/badge/Top.gg-Verified-brightgreen)](https://top.gg/bot/1414901319998767144)
[![Node.js](https://img.shields.io/badge/Node.js-v20+-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Discord.js](https://img.shields.io/badge/Discord.js-v14-5865F2?logo=discord&logoColor=white)](https://discord.js.org/)

**FileFlux is a simple and powerful Discord file converter bot that makes file conversion easy, fast, and accessible directly within Discord.**

FileFlux allows users to convert images, PDF documents, Word documents, and text files between supported formats using simple Discord slash commands. No external conversion website or additional software is required for users.

---

## Features

- **Image Conversion:** Convert JPG, JPEG, PNG, and WEBP images into other supported image formats or PDF.
- **PDF to DOCX:** Convert PDF documents into editable Word documents using Python.
- **DOCX to PDF:** Convert Word documents into PDF format.
- **Text Conversion:** Convert TXT files into Markdown and Markdown files into TXT.
- **Slash Commands:** Simple and easy-to-use `/convert` and `/ping` commands.
- **File Upload Support:** Upload files directly through Discord.
- **File Size Limit:** Supports file uploads up to 10 MB.
- **Automated Processing:** Automatically detects the input file and provides available output formats.

## Supported Conversions

| Source | Target Formats |
|---|---|
| Image (`jpg`, `jpeg`, `png`, `webp`) | Other images, PDF |
| PDF | DOCX |
| DOCX | PDF |
| TXT | MD |
| MD | TXT |

## Slash Commands

### `/ping`

Checks whether FileFlux is online and responding.

**Example response:**

```text
🏓 Pong! Bot is online.
```

### `/convert`

Converts an uploaded file into your selected output format.

**Option:**

- `file` (Attachment) – The file you want to convert. Required.

**How it works:**

1. Enter `/convert` in a Discord channel.
2. Upload the file you want to convert.
3. Select the desired output format from the available options.
4. FileFlux processes the file.
5. Download the converted file directly from Discord.

## Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | Main application runtime |
| Discord.js | Discord bot integration and slash commands |
| Python | Document conversion operations |
| Sharp | Image processing and conversion |
| LibreOffice | Document format conversion |
| pdf2docx | PDF to DOCX conversion |
| PDF-Lib | PDF processing |
| Showdown | Markdown and HTML conversion |
| Docker | Application containerization |

## Project Structure

```text
Convertly/
│
├── docs/
│   └── privacy.html
│
├── converter.py
├── index.js
├── dockerfile
├── package.json
├── package-lock.json
├── README.md
├── LICENSE
├── .dockerignore
└── .gitignore
```

## Prerequisites

Before running FileFlux locally, make sure you have installed:

- Node.js 20 or later
- npm
- Python 3.10 or later
- LibreOffice
- A Discord account
- A Discord application with a bot configured

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/aryanp4200p/Convertly
```

Navigate into the project directory:

```bash
cd Convertly
```

### 2. Install Node.js dependencies

```bash
npm install
```

### 3. Install Python dependencies

```bash
python -m pip install pdf2docx
```

Make sure LibreOffice is installed and accessible from your system PATH.

### 4. Configure environment variables

Create a `.env` file in the root directory.

Add the following variables:

```env
TOKEN=your_discord_bot_token
CLIENT_ID=your_discord_application_id
```

Replace the placeholder values with your actual Discord bot token and application ID.

**Important:** Never share your bot token or commit your `.env` file to GitHub.

### 5. Start the bot

Run:

```bash
npm start
```

If the configuration is correct, FileFlux will connect to Discord and register its slash commands.

## Docker Deployment

FileFlux includes a Dockerfile to simplify application setup and deployment.

Docker automatically installs the required Node.js, Python, LibreOffice, and document conversion dependencies inside the container.

### 1. Build the Docker image

From the project root directory, run:

```bash
docker build -f dockerfile -t convertly .
```

### 2. Run the container

```bash
docker run -d --name convertly-bot --env-file .env -p 3000:3000 --restart unless-stopped convertly:latest
```

### 3. Check container logs

```bash
docker logs -f convertly-bot
```

### 4. Stop the container

```bash
docker stop convertly-bot
```

### 5. Start the container again

```bash
docker start convertly-bot
```

### 6. Check running containers

```bash
docker ps
```

**Note:** Docker must be installed and running on your machine or hosting server. The `.env` file should remain outside the Git repository.

## Environment Variables

| Variable | Description | Required |
|---|---|---|
| `TOKEN` | Discord bot authentication token | Yes |
| `CLIENT_ID` | Discord application/client ID | Yes |

## Privacy and Security

FileFlux processes uploaded files to perform the requested conversion.

- Files are downloaded temporarily for processing.
- Converted files are returned to the user through Discord.
- Temporary conversion files are cleaned up after processing.
- The bot does not use uploaded files to train AI or machine learning models.
- Discord handles the delivery of uploaded and converted attachments through its platform.

For more information, read our [Privacy Policy](docs/privacy.html).

## Troubleshooting

### Bot is not responding

- Check whether the bot is online in your Discord server.
- Verify that the `TOKEN` and `CLIENT_ID` values are correct.
- Check the terminal or Docker logs for errors.
- Ensure the bot has the required Discord permissions.

### Slash commands are not appearing

- Verify that the bot was invited using the `bot` and `applications.commands` OAuth2 scopes.
- Check that command registration completed successfully.
- Restart the bot if necessary.

### PDF conversion fails

- Make sure LibreOffice is installed.
- Verify that the LibreOffice executable is accessible through PATH.
- Confirm that the Python dependencies are installed correctly.

### File conversion fails

- Ensure the uploaded file uses a supported format.
- Check that the file does not exceed the 10 MB limit.
- Try another file if the original is corrupted.
- Check the application logs for additional details.

## Contributing

Contributions, bug reports, and feature suggestions are welcome!

To contribute:

1. Fork this repository.
2. Create a new branch for your changes.

```bash
git checkout -b feature/your-feature-name
```

3. Make your changes.
4. Commit your changes.

```bash
git commit -m "Add: your feature description"
```

5. Push your branch.

```bash
git push origin feature/your-feature-name
```

6. Open a Pull Request.

## License

This project is open source. See the [LICENSE](LICENSE) file for license details.

## Links

- **GitHub Repository:** [Convertly](https://github.com/aryanp4200p/Convertly)
- **Top.gg Listing:** [FileFlux](https://top.gg/bot/1414901319998767144)
- **Report Issues:** [GitHub Issues](https://github.com/aryanp4200p/Convertly/issues)
- **Privacy Policy:** [Read Privacy Policy](docs/privacy.html)

---

**Made for the Discord community.**