znDraw
=========
NES game 'Zombie Nation' draw tool. At least 'game over' string glyphs are drawn with special algorithm. This tool allows to view and compose new glyphs.


Run with MS Excel, enable macroses for convenience with chart enumeration, if you want.


0x18991 - is pointer table for each glyph. 8 pointers per 2 bytes for 8 glyphs of GAMEOVER, note how 4th and 7th pointers are the same. 
First 'G' glyph starts at 0x189b5. 
First 2 bytes are X and Y of glyph draw start position. Next bytes are direction indexes, stored in nybbles. Direction index takes 3 bits, 4th bit is a drawing stop flag. 8 directions, new point is drawn in that direction from previous (dx;dy) - coords are cartesian: 
```
0:( 1; 1)
1:( 1; 0)
2:( 1;-1)
3:( 0;-1)
4:(-1;-1)
5:(-1; 0)
6:(-1; 1)
7:( 0; 1)
8 and higher: end of drawing
```
To view the glyph, open decode tab and paste data from hex editor to 'data input' column (use text by columns and transpose for convenience). 
To edit the glyph, open encode tab, play with dx, dy values to form a new glyph and paste data string back to ROM in hex editor.
