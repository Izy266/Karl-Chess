# Karl's Sun (~ 2500 Elo)

Karl's Sun is a multi-threaded Python-based chess engine designed for playing chess games, analyzing positions, and providing a challenging opponent for players. The engine utilizes a combination of classic chess algorithms, board representation techniques, and modern enhancements for efficient move generation and evaluation.

## Features:

### General:
* UCI Protocol Support: KarlPy follows the Universal Chess Interface (UCI) protocol, allowing seamless integration with various chess interfaces and applications.

### Evaluation:
* **Opening Book**: Karl's Sun utilizes the komodo.bin opening book, an opening book used by the Komodo chess engine, created by the opening book expert Erdogan Gunes
* **PeSTO Board Evaluation**: A Piece-Square Tables Only (PeSTO) evaluation function, developed by Ronald Friederich for his chess engine RofChade, that performs a tapered evaluation to interpolate between piece-square tables values for the opening and endgame.
* **Negamax Framework**: A decision-making algorithm used in game theory and artificial intelligence for two-player zero-sum games that finds the best move by recursifely exploring the game tree with minimax principles.
* **Quiescence Search**: Explores tactical sequences such as captures and promotions to completion until the board state is quiet to limit the horizon effect.
* **Syzygy Endgame Tablebases**: The engine incorporates Syzygy endgame tablebases for positions with up to 4 pieces, enabling precise endgame play.

### Efficiencies:
* **Iterative Deepening with MTD(f)**: Karl's Sun employs the MTD(f) (Memory-enhanced Test Driver with a fixed-depth window) search algorithm in conjunction with iterative deepening. This approach amalgamates the advantages of binary search and memory enhancements to efficiently identify the optimal move.
* **Transposition Table**: Karl's Sun uses a transposition table to store and retrieve previously computed positions, optimizing search performance.
* **Multi-Threading**: The engine uses the parallel search approach lazy SMP for parallel processing, accelerating the search process and resulting in better engine moves.
* **Bitwise Operations**: While the boardstate is stored as a one dimentional array, bitwise operations are used to traverse the board when possible, improving efficiency when generating legal moves.

### Move Ordering:
* **MVV_LVA(Most Valuable Victim - Least Valuable Attacker)**: Karl's Sun employes the MVV_LVA heuristic to prioritize capturing moves based on the value of the victim and attacker pieces, enhancing move ordering of captures.
* **Killer Heuristic**: The engine prioritizes moves that were successful in previous iterations at the same depth, improving chances of obtaining cutoffs early, enhancing search efficiency.
* **Relative History Heuristic**: Karl's Sun utilizes a relative history heuristic to prioritize moves that have historically led to cutoffs in relation to the move's frequency during the search.
* **Countermove Heuristic**: The engine increases the value of moves that caused a cutoff in response to a specific move by the opponent, ordering it earlier


### Pruning:



Getting Started:

Clone the repository:

    git clone https://github.com/yourusername/karlpy-chess-engine.git

Install dependencies:

    pip install -r requirements.txt

Contributions:

Contributions, bug reports, and feature requests are welcome! Feel free to submit pull requests or open issues to help improve KarlPy.
License:

This project is licensed under the MIT License - see the LICENSE file for details.

Adjust the content as needed, and include relevant links to your repository, license file, and any additional documentation or resources.
