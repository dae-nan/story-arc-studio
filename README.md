# Story Arc Studio

A web-based story generation tool that creates narratives using proven story frameworks like Hero's Journey, Three-Act Structure, and Save the Cat.

## Features

- **Multiple Story Templates**: Choose from Hero's Journey, Three-Act Structure, Save the Cat, or create your own custom template
- **Constraint System**: Lock in word count, reading level, moral themes, character rosters, and content restrictions
- **Complete Story Generation**: Get an outline, chapter beats, full story, and comprehension questions
- **Quality Validation**: Automatic checks for word count, beat presence, character consistency, and reading level

## How to Deploy to GitHub Pages

### Quick Setup (5 minutes)

1. **Create a new GitHub repository**
   - Go to https://github.com/new
   - Name it something like `story-arc-studio`
   - Make it public
   - Don't initialize with README (we already have files)

2. **Upload your file**
   - Click "uploading an existing file"
   - Drag and drop `story-arc-studio.html` (or rename it to `index.html` for cleaner URLs)
   - Commit the file

3. **Enable GitHub Pages**
   - Go to your repository Settings
   - Scroll to "Pages" in the left sidebar
   - Under "Source", select "Deploy from a branch"
   - Choose `main` branch and `/ (root)` folder
   - Click Save

4. **Access your site**
   - Your site will be live at: `https://yourusername.github.io/story-arc-studio/`
   - If you renamed the file to `index.html`, that's your URL
   - If you kept it as `story-arc-studio.html`, add that to the URL

### Alternative: Use Git (Command Line)

```bash
# Clone your new empty repository
git clone https://github.com/yourusername/story-arc-studio.git
cd story-arc-studio

# Copy the HTML file
cp /path/to/story-arc-studio.html index.html

# Commit and push
git add index.html
git commit -m "Initial commit: Story Arc Studio"
git push origin main

# Then enable GitHub Pages in Settings as described above
```

## How It Works

### Story Templates

The app comes with three built-in templates:

1. **Hero's Journey** - Classic 12-beat monomyth structure
2. **Three-Act Structure** - Traditional narrative arc with 9 key beats
3. **Save the Cat** - Blake Snyder's 15-beat screenplay structure
4. **Custom Template** - Build your own beat sequence

### Constraints

Set guardrails for your story:
- **Word Count**: Target length (stays within ±10%)
- **Reading Level**: Early Reader, Middle Grade, Young Adult, or Adult
- **Moral Theme**: Optional theme like "Courage" or "Friendship"
- **Characters**: Comma-separated list of character names to include
- **No Scary Content**: Child-friendly filter

### Quality Checks

The app validates each story:
- ✓ Word count within target range
- ✓ All story beats present in correct order
- ✓ Character names used consistently
- ✓ Reading level approximation (via sentence length heuristics)

## Extending the App

### Adding New Templates

Edit the `TEMPLATES` object in the JavaScript:

```javascript
const TEMPLATES = {
    'your-template': {
        name: "Your Template Name",
        beats: [
            "Beat 1",
            "Beat 2",
            "Beat 3",
            // ... more beats
        ]
    }
};
```

Then add it to the select dropdown:

```html
<option value="your-template">Your Template Name</option>
```

### Customizing the AI Prompt

The `buildPrompt()` function constructs the prompt sent to Claude. Modify it to:
- Add new constraint types
- Change the output format
- Adjust tone or style requirements

### Styling

All CSS is in the `<style>` tag. The design uses:
- **Colors**: Warm, literary aesthetic (paper, ink, bronze accent)
- **Fonts**: Crimson Pro (serif) for headings, Work Sans (sans-serif) for body
- **Layout**: Responsive grid that stacks on mobile

## Technical Notes

- **Single File**: Everything (HTML, CSS, JS) in one file for easy GitHub Pages deployment
- **React**: Uses React 18 via CDN (no build step required)
- **API Integration**: Connects to Anthropic's Claude API for story generation
- **Fallback**: Demo data displays if API is unavailable

## Future Enhancements

Ideas for expansion:
- Export stories as PDF or DOCX
- Save/load story projects to browser storage
- Collaborative editing features
- Story visualization (beat timeline)
- Multiple story comparison
- Integration with writing tools

## License

Open source - use and modify as you like!
