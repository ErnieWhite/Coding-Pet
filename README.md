# 🐾 Coding Pet Design Guide

## Project Overview
A desktop application that displays a cute, cartoony digital pet that grows and evolves based on your daily GitHub commit activity!

---

## Core Concept

Your pet starts as a tiny egg and evolves through different stages based on your coding consistency:

**Evolution Stages:**
1. **Egg** (Day 0) - Just starting out
2. **Baby** (Days 1-7) - Your first week of commits
3. **Child** (Days 8-21) - Building the habit
4. **Teen** (Days 22-49) - Getting stronger
5. **Adult** (Days 50-99) - Consistent coder
6. **Master** (100+ days) - Ultimate form!

---

## How Growth Works

### Daily Commit Tracking
- The app checks your GitHub commits once per day
- Each day with at least 1 commit = +1 growth point
- Your pet's stage depends on total growth points accumulated
- Missing a day doesn't reset progress, but the pet might look a bit sad!

### Pet Mood System
- **Happy** - You committed today! (bouncing animation)
- **Content** - Last commit was yesterday (idle animation)
- **Sleepy** - 2-3 days since last commit (yawning)
- **Sad** - 4+ days without commits (droopy ears/eyes)

---

## Technical Architecture

### Main Components to Build

#### 1. **GitHub API Integration**
- Use PyGithub library to fetch commit data
- Store user's GitHub username in config
- Check commits from authenticated user
- Cache results to avoid API rate limits

#### 2. **Pet State Manager**
- Track total commit days
- Calculate current evolution stage
- Determine current mood
- Save/load pet state from JSON file

#### 3. **GUI with Tkinter**
- Main window with pet display area
- Use Canvas widget for pet rendering
- Stats panel showing commit streak info
- Settings panel for GitHub username

#### 4. **Graphics System**
- Use PIL (Pillow) for image handling
- Store pet sprites as PNG files (one per stage/mood combo)
- Implement simple sprite animation (frame switching)
- Optional: Draw simple shapes with Canvas if you want to avoid image files

#### 5. **Background Scheduler**
- Use schedule library or threading
- Check GitHub API once per day (maybe at startup + every 6 hours)
- Update pet state based on new commits
- Show notification when pet evolves

---

## File Structure

```
coding_pet/
├── main.py                 # Entry point, launches GUI
├── pet_state.py           # Pet state management class
├── github_tracker.py      # GitHub API interaction
├── gui.py                 # Tkinter GUI code
├── config.json            # User settings (GitHub username, API token)
├── pet_data.json          # Pet's current state (days, stage, mood)
├── assets/
│   └── sprites/
│       ├── egg.png
│       ├── baby_happy.png
│       ├── baby_sad.png
│       └── ... (more sprite files)
└── requirements.txt       # Python dependencies
```

---

## Key Learning Milestones

### Phase 1: Basic Setup
- Install Python dependencies (tkinter, PyGithub, Pillow)
- Create basic window with Tkinter
- Display a simple shape or image

### Phase 2: GitHub Integration
- Set up GitHub API authentication
- Fetch commit data for a specific date
- Print results to console

### Phase 3: Pet Logic
- Create Pet class with attributes (stage, mood, days)
- Implement evolution logic based on commit days
- Save/load pet state from JSON

### Phase 4: Visual Display
- Display pet sprites based on current stage
- Implement mood changes
- Add basic animations (sprite swapping)

### Phase 5: Polish
- Add commit streak counter
- Create notification system
- Add settings panel
- Style the GUI to look cute!

---

## Fun Features to Add Later

- **Accessories**: Unlock hats, glasses, or bows for your pet
- **Achievements**: Badges for milestones (10 day streak, 100 commits, etc.)
- **Multiple Pets**: Track different repos with different pets
- **Mini-games**: Play with your pet using keyboard
- **Feeding System**: "Feed" your pet with particularly large commits
- **Pet Journal**: View history of your pet's growth

---

## Design Tips for Cuteness

### Visual Style
- **Big eyes** - Classic cute character design
- **Round shapes** - Soft, friendly appearance
- **Pastel colors** - Easy on the eyes
- **Simple expressions** - Easy to read emotions

### Animation Ideas
- Gentle bounce when happy
- Slow blink when content
- Tail/ear droop when sad
- Sparkle effect when evolving

### UI Color Palette Suggestion
- Background: Soft mint green (#B8E6D5)
- Accent: Coral pink (#FF9AA2)
- Text: Dark gray (#4A4A4A)
- Highlights: Golden yellow (#FFD97D)

---

## Getting Started Checklist

- [ ] Set up Python virtual environment
- [ ] Install required libraries
- [ ] Create GitHub personal access token
- [ ] Design or find your first pet sprite (egg stage)
- [ ] Build basic Tkinter window
- [ ] Test GitHub API connection
- [ ] Implement pet state saving/loading
- [ ] Connect everything together!

---

## Resources to Explore

- **PyGithub Documentation**: How to interact with GitHub API
- **Tkinter Tutorial**: Build GUI applications
- **Pillow (PIL) Guide**: Image manipulation in Python
- **Sprite Art Tools**: Piskel, Aseprite, or even MS Paint for simple designs

---

Good luck with your coding pet! Remember: the pet grows as you learn, so every commit counts! 🌱✨
