# Calico Board Game - Android App

A digital implementation of the [Calico](https://boardgamegeek.com/boardgame/283155/calico) board game for Android, built as a university project (CS 301).

## Overview

Calico is a tile-placement strategy game where players fill a 7x7 quilt board with colorful, patterned patches to score points. Players earn points by:

- **Attracting Cats** — grouping patches with patterns that match cat preferences
- **Completing Goals** — arranging tiles around goal spaces to satisfy specific pattern/color requirements
- **Collecting Buttons** — forming groups of same-colored patches

### Cats

| Cat     | Points | Requirement           |
|---------|--------|-----------------------|
| Cuddles | 3      | 3+ matching patterns  |
| Smokey  | 5      | 4+ matching patterns  |
| Stripe  | 7      | 5+ matching patterns  |

### Goal Tiles

Six goal types with varying point values based on pattern/color arrangements around each goal space (e.g., AAA BBB, AA BB CC, AAAA BB).

## Game Flow

1. Select a patch from your hand (2 patches)
2. Place it on your board
3. Draw a new patch from the community pool (3 shared patches)
4. Confirm your move (or undo and retry)

The game ends when all board spaces are filled. Highest score wins.

## Features

- **1-4 players** on a single device
- **Two AI opponents:**
  - Dumb Computer — makes random moves
  - Smart Computer — uses strategic decision-making
- **Network multiplayer** support via TCP (port 2234)
- **Undo** moves within a turn
- **Objectives menu** overlay showing cat/goal status

## Requirements

- Android Studio (Arctic Fox or newer recommended)
- Android SDK 34 (compile SDK)
- Minimum device/emulator: Android 7.0 (API 24)

## Getting Started

1. Clone the repository:
   ```
   git clone <repository-url>
   ```
2. Open the project in Android Studio (File → Open → select project folder)
3. Wait for Gradle sync to complete
4. Click **Run** (▶) or press `Shift+F10`
5. Select an emulator (API 24+) or connected Android device

No additional configuration is required — the default run configuration works out of the box.

## Project Structure

```
app/src/main/java/edu/up/cs301/
├── Calico/                     # Game-specific code
│   ├── CalicoMainActivity.java # Entry point and player config
│   ├── CalicoState.java        # Master game state
│   ├── CalicoLocalGame.java    # Game logic controller
│   ├── CalicoHumanPlayer.java  # Human player UI
│   ├── CalicoComputerPlayer1.java  # Random AI
│   ├── CalicoComputerPlayer2.java  # Strategic AI
│   ├── Board.java              # 7x7 board representation
│   ├── Patch.java              # Tile (color + pattern)
│   ├── GoalPatch.java          # Scoring goal tiles
│   ├── Cat.java                # Cat scoring objectives
│   └── ...                     # Game actions (Select, Place, Undo, etc.)
└── GameFramework/              # Reusable game engine
    ├── Game/                   # Core game interfaces
    ├── Players/                # Player base classes
    ├── Actions/                # Action base classes
    └── Utilities/              # Logging, networking, etc.
```

## Tech Stack

- **Language:** Java
- **UI:** Android XML layouts with drawable vector graphics
- **Build:** Gradle (Kotlin DSL)
- **Testing:** JUnit 4, Espresso

## Authors

University of Portland — CS 301 Game Project
