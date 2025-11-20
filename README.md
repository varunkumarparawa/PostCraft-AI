# LinkedIn Post Generator 🚀

An AI-powered web application that generates compelling LinkedIn posts using Google's Gemini 2.5 Flash model. Create professional, engaging posts tailored to your audience in seconds.

## Features

✨ **AI-Powered Generation** - Uses Gemini 2.5 Flash for high-quality content
🎨 **Customizable Options** - Choose style, audience, tone, and length
😊 **Emoji Support** - Toggle emojis on/off for your posts
📋 **Copy & Regenerate** - Easily copy posts or generate alternatives
📊 **Word/Character Count** - Real-time statistics for each post
📱 **Fully Responsive** - Works seamlessly on desktop and mobile devices

## Tech Stack

- **Frontend**: React 19, Next.js 16 (App Router)
- **Styling**: Tailwind CSS v4, shadcn/ui components
- **AI Model**: Google Gemini 2.5 Flash API
- **Language**: TypeScript
- **Build**: Turbopack

## Getting Started

### Prerequisites

- Node.js 18+ installed
- Google Gemini API key ([Get it here](https://makersuite.google.com/app/apikey))

### Installation

1. **Clone the repository**
   \`\`\`bash
   git clone <your-repo-url>
   cd linkedin-post-generator
   \`\`\`

2. **Install dependencies**
   \`\`\`bash
   npm install --legacy-peer-deps
   \`\`\`

3. **Create `.env.local` file**
   \`\`\`bash
   GEMINI_API_KEY=your_api_key_here
   \`\`\`

4. **Start development server**
   \`\`\`bash
   npm run dev
   \`\`\`

5. **Open in browser**
   \`\`\`
   http://localhost:3000
   \`\`\`

## Usage

1. **Enter a Topic** - Write what you want to post about
2. **Select Options**:
   - **Style**: Professional, Storytelling, Tips, Motivational, Informative
   - **Audience**: Students, Professionals, Managers, Entrepreneurs
   - **Tone**: Formal, Friendly, Inspirational
   - **Length**: Short, Medium, Long
   - **Emojis**: Toggle on/off
3. **Generate Post** - Click the "Generate Post" button
4. **Copy or Regenerate** - Copy to clipboard or regenerate for alternatives

## API Integration

The app uses the Google Generative Language API (Gemini 2.5 Flash) directly. The API route:
- Receives post parameters from the frontend
- Constructs an optimized prompt
- Calls Gemini API
- Returns the generated post

### API Endpoint

\`\`\`
POST /api/generate-post
\`\`\`

**Request Body**:
\`\`\`json
{
  "topic": "AI in business",
  "style": "Professional",
  "audience": "Professionals",
  "tone": "Formal",
  "length": "Medium",
  "emojiEnabled": true
}
\`\`\`

**Response**:
\`\`\`json
{
  "post": "Generated LinkedIn post text..."
}
\`\`\`

## Environment Variables

Create a `.env.local` file in the project root:

\`\`\`
GEMINI_API_KEY=your_google_gemini_api_key
\`\`\`

**Never commit this file to GitHub** - it's already in `.gitignore`

## Project Structure

\`\`\`
├── app/
│   ├── api/
│   │   └── generate-post/
│   │       └── route.ts          # API endpoint for post generation
│   ├── layout.tsx                # Root layout
│   ├── page.tsx                  # Home page
│   └── globals.css               # Global styles
├── components/
│   └── linkedin-post-generator.tsx  # Main component
├── public/                        # Static assets
├── .env.local                    # Environment variables (not in repo)
└── package.json
\`\`\`

## Development

### Run Development Server
\`\`\`bash
npm run dev
\`\`\`

### Build for Production
\`\`\`bash
npm run build
\`\`\`

### Start Production Server
\`\`\`bash
npm start
\`\`\`

### Linting
\`\`\`bash
npm run lint
\`\`\`


**"API key not configured" error**
- Make sure `.env.local` exists in your project root
- Verify `GEMINI_API_KEY` is set correctly
- Restart the dev server after adding `.env.local`

**"No content in API response" error**
- Check that your API key is valid
- Ensure the Generative Language API is enabled in Google Cloud Console
- Try a different topic

**App shows empty topic field on refresh**
- Clear browser cache: `Ctrl + Shift + Delete`
- Hard refresh page: `Ctrl + Shift + R`
- Delete `.next` folder and restart server

## Contributing

Feel free to fork, modify, and submit pull requests!

## License

MIT License - feel free to use this project for personal or commercial purposes.

## Support

If you encounter any issues:
1. Check the [Gemini API documentation](https://ai.google.dev/docs)
2. Review error messages in browser console (F12)
3. Ensure `.env.local` is properly configured

---

**Made with ❤️ using Gemini AI and Next.js**
