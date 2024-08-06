# Emotional LLMs: Evaluating Decision-Making in Game Theory Contexts

## Abstract

This research introduces a novel framework for integrating emotions into Large Language Models (LLMs) and evaluates their decision-making processes in various game-theoretical settings. We examine the alignment of LLMs with human behavior by simulating decision-making in bargaining and multiplayer games, focusing on game-theoretical scenarios such as Dictator, Ultimatum, and other strategic games.

## Project Structure

```
.
├── README.md
├── prompts/
│   └── {language}/
│       ├── agent/
│       ├── emotions/
│       └── games/
├── run_division_game.py
├── run_exps_division_game.py
├── run_table_game.py
└── src/
```

## Key Features

- Novel framework for integrating emotions into LLMs' decision-making in game theory
- Experimental study across various strategic games
- Analysis of emotional and strategic biases in LLM decision-making
- Comparison of proprietary and open-source LLM performance
- Multi-language support (English & Russian)

## Games

The framework supports integration of:
- One-shot bargaining games (Dictator, Ultimatum)
- 2-player repeated games (e.g., Prisoner's Dilemma)
- Multi-player games (Public Goods, and El Farol Bar games)

## Installation

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)
- Git

### Steps

1. Clone the repository:
   ```
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the required Python packages:
   ```
   pip install -r requirements.txt
   ```

   If `requirements.txt` doesn't exist, create it with the following content:
   ```
   openai
   pandas
   tqdm
   pydantic
   python-dotenv
   ```

4. Set up environment variables:
   - Create a `.env` file in the root directory of the project
   - Add your OpenAI API key to the `.env` file:
     ```
     OPENAI_API_KEY=your_api_key_here
     ```

5. If there are any additional data files or models required, place them in the appropriate directories within the project structure.

### Troubleshooting

- If you encounter issues with the OpenAI API, ensure your API key is correctly set in the `.env` file and that you have sufficient credits.
- For any import errors, make sure all required packages are installed and that you're running Python from the correct virtual environment.
- If you face issues with file paths, check that you're running the scripts from the root directory of the project.

### Note

This project uses environment variables to manage sensitive information like API keys. Never commit your `.env` file or share your API keys publicly.

## Usage

### Running Division Game Experiments

To run experiments with bargaining games:

```bash
python run_exps_division_game.py
```

### Running a Single Division Game

To run a single division game:

```bash
python run_division_game.py
```

### Running Table Games

To run table games:

```bash
python run_table_game.py
```

## Prompt Structure

The `prompts` directory contains language-specific prompts organized as follows:

- `agent/`: Contains prompts for agent behavior, memory updates, etc.
  - `memory_update.txt`: Prompt for updating agent's memory after current round (not for bargaining)
  - `emotions/`: Folder with prompts for questioning emotions and inserting them into memory
  - `game_settings/`: Folder with prompts for defining environment, conditions, and general prompt for initialization memory of agent - `outer_emotions/`: Folder with prompts for questioning what emotions to demonstrate and how to describe them to coplayer (not for bargaining)
- `emotions/`: Descriptions for initial agents' emotions
- `games/`: Game-specific prompts and rules
  - `rewards.json`: Reward matrix
  - `rules1.txt`: Rules described for the first player
  - `rules2.txt`: Rules described for the second player

## Languages

Games are currently available in English & Russian. The `{language}` in the directory structure is the chosen language's lowercase name (english, russian).

## Main Findings

1. Emotions significantly alter LLM decision-making, regardless of alignment strategies.
2. GPT-4 shows less alignment with human emotions but breaks alignment in 'anger' mode.
3. GPT-3.5 and Claude demonstrate better alignment with human emotional responses.
4. Proprietary models outperform open-source and uncensored LLMs in decision optimality.
5. Medium-size models show better alignment with human behavior.
6. Adding emotions helps model cooperation and coordination during games.

## Future Work

- Validate findings with both proprietary and open-source LLMs
- Explore finetuning of open-source models on emotional prompting
- Investigate multi-agent approaches for dynamic emotions
- Study the impact of emotions on strategic interactions in short- and long-term horizons


## Contributing

We welcome contributions to this project! If you're interested in contributing, please follow these steps:

1. Fork the repository
2. Create a new branch for your feature (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Contact

For questions or feedback, please see the contribution section.

## Acknowledgements
- OpenAI for providing the GPT models used in this research
- The game theory community for foundational work in this field

---

This project is part of ongoing research in the field of AI ethics and decision-making. We encourage collaboration and welcome discussions on the implications and applications of emotion-aware AI in strategic scenarios.
```
