# DATA533_Project

This RPG game package is designed as a turn-based battle simulator where players face off against NPCs in an arena, utilizing items and skills to gain an edge in combat. The package is organized into two sub-packages: Character and Gameplay. Each sub-package contains two modules, each with at least three methods or functions, supporting various aspects of the game. Inheritance is implemented in the Character sub-package.

1. Character Sub-Package
- Modules:
    - player.py: Defines the Player class, inheriting from Character.
        - generate_stats(): Randomly assigns stats (HP, ATK, DEF, etc.) for the player.
        - use_item(item): Applies an item’s effect (e.g., healing or stat boost).
        - take_damage(amount): Reduces the player’s HP based on incoming damage.
        - dodge_attack(): Gives the player a chance to dodge an attack.
    - npc.py: Contains the NPC class, also inheriting from Character.
        - generate_stats(): Randomly assigns stats for the NPC.
        - choose_attack(): Determines the NPC’s attack move each round.
        - take_damage(amount): Reduces the NPC’s HP based on incoming damage.
        - taunt_player(): Outputs a random taunt aimed at the player during combat.
2. Gameplay Sub-Package
- Modules:
    - events.py: Manages random events that allow players to acquire items.
        - generate_event(): Randomly selects an event, such as finding an item.
        - get_item(): Assigns an item to the player from the event.
        - apply_item_effect(player, item): Applies the item’s effect to the player.
    - combat.py: Manages the turn-based combat system.
        - attack(attacker, defender): Executes an attack from one character to another.
        - calculate_critical_hit(attacker): Adds an element of chance by allowing critical hits that deal bonus damage.
        - start_combat(player, npc): Initiates and runs the combat rounds between player and NPC.
        - check_victory(player, npc): Checks HP to determine if either the player or NPC has won.
    - interface.py: Display all the necessary information and gain player's input.
        - display_event_description(event): Describes the random event that occurs, providing context to the player.
        - display_stats(character): Displays the current stats (e.g., HP, ATK, DEF) of the given character (Player or NPC).
        - display_combat_round(round_number, player, npc): Shows the current combat round, description of the player’s and the npc’s movements.
        - get_player_action(): Prompts the player to choose an action during their turn (e.g., use items, do nothing).
        - display_player_action_result(action): Describes the effects of the actions the player take.
        - display_last_message(): Displays the result of the combat.
        