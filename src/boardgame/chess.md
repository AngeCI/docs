# Web Chess Board
## Position format

Each piece is represented by a hexadecimal digit, then encode the whole number with base64. This application includes a converter that can convert between FEN format and the custom base64 position format.

| Piece  | White | Black |
| :----- | :---- | :---- |
| King   | 1     | 9     |
| Queen  | 2     | a     |
| Rook   | 3     | b     |
| Knight | 4     | c     |
| Bishop | 5     | d     |
| Pawn   | 6     | e     |

Empty squares are represented by 0.

Addtional informations such as castling rights, en passant files and number of turns are encoded after a colon.
| Bit index | Meaning |
| -- | -- |
| 0 | Side to move, 0 for white, 1 for black. |
| 1 | Black’s long castle |
| 2 | Black’s short castle |
| 3 | White’s long castle |
| 4 | White’s short castle |
| 5-7 | En passant file, only the file is encoded. 0 for a-file, 7 for h-file. |
| 8 | En passant availability |
| 9-14 | Number of turns since the last capture or pawn move. |
| 15-23+ | Number of turns since the beginning of the entire game. |

The starting position encoded into the custom base64 position format is: `vNqdy+7u7u4AAAAAAAAAAAAAAAAAAAAAZmZmZjRSFUM:eAAA`

## Moves format

Moves are represented by the source square and the destination square only. Each square is represented by a base64 character. This application includes a converter that can convert between algebraic notation, UCI format and the custom base64 moves format.

```
     Black
A B C D E F G H
I J K L M N O P
Q R S T U V W X
Y Z a b c d e f
g h i j k l m n
o p q r s t u v
w x y z 0 1 2 3
4 5 6 7 8 9 + /
     White
```

## Sample game
```
Regular algebraic notation:
1. e4 h5
2. d4 a6
3. Nc3 h4
4. Bg5 Nc6
5. d5 e5
6. Bxd8 b6
7. Bxc7 Nge7
8. dxc6 f6
9. Nd5 a5
10. cxd7+ Kxd7
11. Bb5+ Ke6
12. Nf4+ Kf7
13. Bc4+ Be6
14. Bxe6+ Ke8
15. Qd8+ Rxd8
16. Bxd8 Ng6
17. Nxg6 a4
18. O-O-O Bc5
19. Nxh8 Bd4
20. Bc7 Ke7
21. Bf5 b5
22. Nf3 a3
23. Nxd4 g6
24. Nxg6+ Ke8
25. Nxb5 axb2+
26. Kxb2 Kf7
27. Rd7+ Ke8
28. Re7#

UCI format:
e2e4 h7h5 d2d4 a7a6 b1c3 h5h4 c1g5 b8c6 d4d5 e7e5 g5d8 b7b6 d8c7 g8e7 d5c6
f7f6 c3d5 a6a5 c6d7 e8d7 f1b5 d7e6 d5f4 e6f7 b5c4 c8e6 c4e6 f7e8 d1d8 a8d8
c7d8 e7g6 f4g6 a5a4 e1c1 f8c5 g6h8 c5d4 d8c7 e8e7 e6f5 b6b5 g1f3 a4a3 f3d4
g7g6 h8g6 e7e8 d4b5 a3b2 c1b2 e8f7 d1d7 f7e8 d7e7

Custom base64 moves format:
0kPfzjIQ5qfn6eBSjbMceDJRDKGMbSNVqbQYSLEL9ZLUblUNZiCUiUNE7DADKDMWlWYg86FaWH
ajDKEMUdRZ+tgotjOWHWMEjZox6xEN7LNELM
```
