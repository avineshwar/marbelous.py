marbelous.py
============

Python interpreter for Marbelous

Marbelous is an esoteric programming language based on numbered marbles falling down a Rube Goldberg like board full of devices that move and manipulate the marbles.

Creation of this language was inspired by conversation in the Programming Puzzles & Code Golf StackExchange [chat room](http://chat.stackexchange.com/rooms/240/the-nineteenth-byte), forked to a [dedicated chat room](http://chat.stackexchange.com/rooms/16230/marbelous-esolang-design) later.

Credit for the original idea goes to cjfaure.
Additional language design input from Martin Büttner, Nathan Merrill, overactor, sparr, githubphagocyte, es1024, VisualMelon.

First versions of interpreter by sparr.

Example program (more in examples/):

    # calculates the nth fibonacci number, recursively
    I0 I0 I0 .. # three copies of I0, call them A B C
    -- S0 <2 O0 # decrement A, hold B for sync, return C if it's <2
    S0 -- <5 -- # hold A for sync, decrement B, divert and decrement C if it's <5
    -- MB S0 O0 # decrement A, recurse with B, release sync or return C-1
    MB .. \/ .. # recurse with A, do nothing with B, trash C
    \\ O0 .. .. # add A to B and return it
