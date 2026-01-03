## Position format

Each piece is represented by a hexadecimal digit, then encode the whole number with base64. `converter.html` includes a converter that can convert between FEN format and the custom base64 position format.

| Piece  | White | Black |
| :----- | :---- | :---- |
| King / General (將/帥)   | 1     | 9     |
| Advisor (士/仕)  | 2     | a     |
| Bishop / Elephant (象/相) | 3     | b     |
| Knight / Horse (馬/傌) | 4     | c     |
| Rook (車/俥)   | 5     | d     |
| Cannon (炮/砲/包)   | 6     | e     |
| Pawn/Soldier (卒/兵)   | 7     | f     |

Empty squares are represented by 0.
