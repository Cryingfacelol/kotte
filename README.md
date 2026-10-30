# Bomberman World — REASONABLE chaos

**Student:** Eva Kristina Sprinchorn

## How to play

- **Controls:** Use WASD to move, spawn bomb with SPACEBAR, press R to restart in win or lose menu. Press Q to quit. 
- **Objective and rules:** Kill 10 enemies to win, if health falls to 0 you lose, if you win and lose at the same time you will win, a blue power up spawns at game starts: it increases bomb range to 5.
- **Configurations / demo setup:** Default - no special setup required.


## Features and validation

(delete this pre-amble before submitting the assignment) Complete the five required features and three extensions of your choice. For each row, document **at least one useful check: what you tested, what you observed, and how the result compares with the expected behaviour**. One or two sentences per feature are enough. Choose a check that could reveal a mistake, such as a boundary case or interaction.

Use the practical checks in the assignment to validate the acceptance conditions during development; this table is a small sample of that work. Manual play in a small, repeatable setup is sufficient. You can also use a debugger, temporary logging, or small scenarios set up in code. Screenshots, recordings, automated tests etc are welcome, but not required. Be ready to explain the relevant rules in your code.

| Feature | Check, observed result, and expected behaviour |
| --- | --- |
| 1. Player damage and death | Tested the death of player when it deleted player. The game crashed due to an assert warning about a nullptr issue. It was an expected issue as I could not just delete the player_handle the way the others are deleted. I made the program never run that function using player_handle when player was erased, essentially solving the issue. |
| 2. Round states and objective | I checked whether the transitions and everything happened when expected, killing myself and winning several times. All transitions were smooth with no leftover behaviour. Expected behaviour was achieved|
| 3. Safe restart | I tried restarting several times in a row. Realised that the initialisation was working but the erasure of previous game was not working as intended. I made separate clear functions within all of the structs I needed to clear. then it crashed. realised I cleared the cells wrong. Fixed that and then expected behaviour of complete and safe restart was met.|
| 4. Solid bombs with owner escape | I places several bombes and tried several things like staying inside them then placing a new one. I could not walk through and be blocked in a reliably constant manner. This was not the expected behaviour. Looked over the code and made invincibility a member of the bomb. Worked as expected after.|
| 5. Blast-range pickup | Tested the range of a bomb placed before pickup after pickup. The range was not increased. Worked as expected. No changes had to be made. |
| 6. Multiple bombs per owner | Tried placing to replace detonated bombs, tested the power-up. The bombs replace well and had no issue of exceeding the limit, the power up activated on all bombs placed after it was picked up. Behaviour was expected.|
| 7 Chain reactions | Tested placing many bombs in rows and around enemies. The bombs in blast effect also detonated. Behaviour was expected. Added a delay to the chain though because it was instant. |
| 8 temporary invulnerability | walked into several enemies and blast effect at the same time. The damage was only taken once before invulnerability kicked in. this was the expected behaviour. Gave a small moment of invulnerability with no colour for play experience. |


**Known issues:** bombs are not visible when placed on a crate.

## Sources and assistance

This project builds on the shared Kotte foundations.

Kuznietsov Illia - who as a very helpful rubber duck. 
The cpp reference website - very useful for finding and understanding functions. 
The original kotte code - inspired many of my code solutions(apologies for the butchery). 