# ⚔️ sword-script - Scripture Memorization Tool

**S**cripture **W**ord **O**f **R**ighteousness **D**aily

A gamified Bible verse memorization tool that turns your terminal into an interactive scripture memory system. Train your mind with God's Word using spaced repetition and progressive difficulty levels.

> *"For the word of God is alive and active. Sharper than any double-edged sword, it penetrates even to dividing soul and spirit, joints and marrow; it judges the thoughts and attitudes of the heart."* - Hebrews 4:12

## 🎯 Features

- **5 Unique ASCII Sword Designs** - Random sword artwork on each launch (with rainbow colors via lolcat)
- **Spaced Repetition Learning** - 70% review of known verses, 30% new content
- **Progressive Difficulty Levels** - 4 mastery levels from beginner to expert
- **Smart Fuzzy Matching** - Accepts answers with 85%+ similarity (handles typos gracefully)
- **Progress Tracking** - Persistent storage of your verse mastery journey
- **Interactive Feedback** - Cowsay-powered verse display with helpful hints
- **KJV Translation** - Uses the King James Version via bible-api.com

## 📋 Prerequisites

### Required Dependencies

```bash
# Ubuntu/Debian
sudo apt install jq cowsay lolcat curl bc python3 python3-pip

# macOS (via Homebrew)
brew install jq cowsay lolcat curl bc python3

# Python package (installed automatically on first run)
pip3 install rapidfuzz
```

## 🚀 Installation

### Quick Install

```bash
# Download the script
curl -O https://raw.githubusercontent.com/Trust-Worthy/sword-script/main/sword-script.sh

# Make it executable
chmod +x sword-script

# Run it!
./sword-script
```

### Add to Startup (Optional)

To run SWORD every time you open your terminal:

**For Bash:**
```bash
echo "./path/to/sword-script" >> ~/.bashrc
```

**For Zsh:**
```bash
echo "./path/to/sword-script" >> ~/.zshrc
```

**For Fish:**
```bash
echo "./path/to/sword-script" >> ~/.config/fish/config.fish
```

## 🎮 How to Use

### Basic Gameplay

1. **Launch the script** - A random sword appears with Hebrews 4:12
2. **Read the challenge** - You'll see either REVIEW or NEW mode
3. **Type the verse** - Enter the scripture text as accurately as possible
4. **Get feedback** - See your accuracy percentage and level up on success!

### Commands

- **Type the verse** - Match the displayed scripture
- **`skip`** - Skip to next verse without penalty
- **`quit`** - Exit the program

### Difficulty Levels

| Level | Description | Display |
|-------|-------------|---------|
| **Level 1** | Full verse shown | Complete text via Tux |
| **Level 2** | Skeleton hints | First letter of each word |
| **Level 3** | No hints initially | Only "???" shown |
| **Level 4** | Mastered | Rarely appears for review |

### Progression System

- **Accuracy threshold:** 85%+ similarity required to advance
- **Review ratio:** 70% of practice is reviewing lower-level verses
- **New content:** 30% chance of encountering a new verse
- **Hints:** After 2 failed attempts at Level 3, skeleton hint appears
- **Reveal:** After 3 failed attempts, full verse is revealed

## 📊 Progress Tracking

Your progress is automatically saved to `~/.bible_progress` in the format:
```
John 3:16|2
Romans 8:28|3
Philippians 4:13|4
```

Each line contains:
- **Reference** - Bible verse citation
- **Level** - Current mastery level (1-4)

### View Your Progress

```bash
cat ~/.bible_progress
```

### Reset Your Progress

```bash
rm ~/.bible_progress
```

## ⚙️ Configuration

Edit these variables at the top of the script:

```bash
VERSION="kjv"          # Bible translation (kjv, web, etc.)
CATEGORY="random"      # Verse category (random, gospels, etc.)
PROGRESS_FILE="$HOME/.bible_progress"  # Storage location
MASTERY_LEVEL=4        # Maximum mastery level
```

### Available Bible Translations

- `kjv` - King James Version (default)
- `web` - World English Bible
- `bbb` - Biblia Biblica Brasilia
- `clementine` - Clementine Latin Vulgate
- `almeida` - João Ferreira de Almeida

## 🎨 ASCII Sword Gallery

The script randomly selects from 5 different sword designs:

1. **Diagonal Blade** - A sleek angled sword
2. **Classic Longsword** - Traditional medieval design
3. **Curved Scimitar** - Middle Eastern style
4. **Ornate Broadsword** - Decorated with runes
5. **Simple Rapier** - Minimalist piercing blade

## 🐛 Troubleshooting

### "Missing dependencies" error
Install all required packages listed in Prerequisites section.

### Python rapidfuzz error
```bash
pip3 install rapidfuzz --user
```

### API connection issues
Check your internet connection. The script requires access to `bible-api.com`.

### Cowsay not displaying properly
Ensure your terminal supports UTF-8 encoding and has sufficient width (80+ columns recommended).

### Lolcat colors not showing
Some terminals don't support ANSI colors. Try a different terminal emulator or remove `| lolcat` from the script.

## 🤝 Contributing

Contributions are welcome! Areas for improvement:

- Additional Bible translations
- More sword ASCII art designs
- Custom verse categories (Psalms, Proverbs, etc.)
- Achievement system
- Statistics dashboard
- Mobile app version

## 📜 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- **Bible API** - bible-api.com for providing free scripture access
- **Cowsay** - For the iconic ASCII animal art
- **Lolcat** - For rainbow terminal colors
- **RapidFuzz** - For intelligent fuzzy string matching
- **The Holy Bible** - The eternal Word of God

## 💡 Tips for Success

1. **Daily practice** - Consistency beats intensity in memorization
2. **Say it aloud** - Speaking engages more memory pathways
3. **Start small** - Don't be discouraged by low initial accuracy
4. **Focus on meaning** - Understanding helps retention
5. **Review regularly** - The script handles this automatically at 70% review rate
6. **Pray first** - Ask God to help you hide His Word in your heart


---

*"Thy word have I hid in mine heart, that I might not sin against thee."* - Psalm 119:11 (KJV)

**May your sword stay sharp!**
