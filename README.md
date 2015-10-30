# Displaying a Tic Tac Toe Board

## Overview

A tic tac toe board can be represented by an array of 9 string elements containing the state of that cell in the board.

An empty board would be:
```ruby
board = [" "," "," "," "," "," "," "," "," "]
```
Representing:
```
   |   |   
-----------
   |   |   
-----------
   |   |   
```

A board with an "X" in the middle:
```ruby
board = [" ", " ", " ", " ", "X", " ", " ", " ", " "]
```
Representing:
```
   |   |   
-----------
   | X |   
-----------
   |   |   
```


A board with X winning via filling the top row:
```ruby
board = ["X", "X", "X", " ", " ", " ", " ", " ", " "]
```
Representing:
```
 X | X | X
-----------
   |   |   
-----------
   |   |   
```

A random board after 5 turns:
```ruby
board = ["O", "X", " ", " ", "X", " ", "X", "O", " "]
```
Representing:
```
 O | X |   
-----------
   | X |   
-----------
 X | O |   
```   

A board entirely filled with "O":
```ruby
board = ["O", "O", "O", "O", "O", "O", "O", "O", "O"]
```
Representing:
```
 O | O | O
-----------
 O | O | O
-----------
 O | O | O
```   

Etc...

Our goal is to build a method `display_board` that accepts a board array as an argument and uses the data in that array to correctly print out an accurate representation of the Tic Tac Toe board from the player's perspective based on the data in the array.

For example, given a correctly defined `display_board`:

```ruby
board = ["O", "X", " ", " ", "X", " ", "X", "O", " "]
display_board(board)
```

Should print:
```
 O | X |   
-----------
   | X |   
-----------
 X | O |   
```

The board follows the following format:

1. When the board is displayed there are three characters per cell. An empty cell is <code>"&nbsp;&nbsp;&nbsp;"</code> and a filled cell is `" X "`
2. Three cells per a row.
3. The middle cell in a row is bordered by 2 `|` (pipes): ` O | X |   `
4. Three rows on the board.
5. Rows are separated by: `-----------`

## Objectives

1. Define a method that accepts an argument.
2. Use the argument within the method.
3. Read data from an array.
4. Print out a multi-line dynamic string using Interpolation

## Instructions

1. Define your `display_board` method in `lib/display_board.rb`
2. Get the test suite passing by running `learn`
3. Submit your solution.

## Hint: The `learn --fail-fast` test flag

To ensure that your `display_board` method honestly works as expected, we had to write a lot of tests to flex the different situations that might occur. When you run `learn`, you're going to see lots of failing tests that are all basically failing for the same reason - `display_board` isn't behaving as desired. It might be easier to deal with one test failure at a time and scrolling through the output of 12 failures isn't helpful.

You can limit your test run to stop at the first failure it encounters so that you only see 1 failure and can easily focus on it. By focusing on a single failure, you can quickly change your method based on that failure and re-run the test suite and see if the change solved that single failure. Although this lengthens the command each time, you can instantly redo your last entered command by tapping the Up arrow on your keyboard so you don't have to type the whole thing each time.

It's helpful, for example:

```
[23:19:40] (master) ttt-4-display_board
// ♥ learn

#display_board in 'lib/display_board.rb
  accepts a board as an argument
  various game situations
    prints a blank board when the board array is empty (FAILED - 1)
    prints a board with an X in the center position (FAILED - 2)
    prints a board with O in the top left (FAILED - 3)
    prints a board with an X in the center and an O in the top left (FAILED - 4)
    prints a board with X winning via the top row (FAILED - 5)
    prints a board with O winning via the bottom row (FAILED - 6)
    prints a board with X winning in a top left to bottom right diagonal (FAILED - 7)
    prints a board with O winning in a top right to bottom left diagonal (FAILED - 8)
    prints arbitrary arrangements of the board (FAILED - 9)
    prints an entire board full of Xs (PENDING: Can you copy the syntax of the tests above to write a test for a board entirely filled with Xs?)
    prints an entire board full of Os (PENDING: Can you copy the syntax of the tests above to write a test for a board entirely filled with Os?)

Pending: (Failures listed here are expected and do not affect your suite's status)

  1) #display_board in 'lib/display_board.rb various game situations prints an entire board full of Xs
     # Can you copy the syntax of the tests above to write a test for a board entirely filled with Xs?
     # ./spec/display_board_spec.rb:132

  2) #display_board in 'lib/display_board.rb various game situations prints an entire board full of Os
     # Can you copy the syntax of the tests above to write a test for a board entirely filled with Os?
     # ./spec/display_board_spec.rb:164


Failures:

  1) #display_board in 'lib/display_board.rb various game situations prints a blank board when the board array is empty
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30dcba8>
     # ./spec/display_board_spec.rb:11:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:11:in `block (3 levels) in <top (required)>'

  2) #display_board in 'lib/display_board.rb various game situations prints a board with an X in the center position
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30d75b8>
     # ./spec/display_board_spec.rb:23:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:23:in `block (3 levels) in <top (required)>'

  3) #display_board in 'lib/display_board.rb various game situations prints a board with O in the top left
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30d5830>
     # ./spec/display_board_spec.rb:38:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:38:in `block (3 levels) in <top (required)>'

  4) #display_board in 'lib/display_board.rb various game situations prints a board with an X in the center and an O in the top left
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30d74a0>
     # ./spec/display_board_spec.rb:52:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:52:in `block (3 levels) in <top (required)>'

  5) #display_board in 'lib/display_board.rb various game situations prints a board with X winning via the top row
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30ce8a0>
     # ./spec/display_board_spec.rb:64:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:64:in `block (3 levels) in <top (required)>'

  6) #display_board in 'lib/display_board.rb various game situations prints a board with O winning via the bottom row
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30ccd20>
     # ./spec/display_board_spec.rb:76:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:76:in `block (3 levels) in <top (required)>'

  7) #display_board in 'lib/display_board.rb various game situations prints a board with X winning in a top left to bottom right diagonal
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30c7780>
     # ./spec/display_board_spec.rb:88:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:88:in `block (3 levels) in <top (required)>'

  8) #display_board in 'lib/display_board.rb various game situations prints a board with O winning in a top right to bottom left diagonal
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30c5c00>
     # ./spec/display_board_spec.rb:100:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:100:in `block (3 levels) in <top (required)>'

  9) #display_board in 'lib/display_board.rb various game situations prints arbitrary arrangements of the board
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007fede30c43a0>
     # ./spec/display_board_spec.rb:112:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:112:in `block (3 levels) in <top (required)>'

Finished in 0.00296 seconds (files took 0.08249 seconds to load)
12 examples, 9 failures, 2 pending

Failed examples:

rspec ./spec/display_board_spec.rb:8 # #display_board in 'lib/display_board.rb various game situations prints a blank board when the board array is empty
rspec ./spec/display_board_spec.rb:20 # #display_board in 'lib/display_board.rb various game situations prints a board with an X in the center position
rspec ./spec/display_board_spec.rb:33 # #display_board in 'lib/display_board.rb various game situations prints a board with O in the top left
rspec ./spec/display_board_spec.rb:47 # #display_board in 'lib/display_board.rb various game situations prints a board with an X in the center and an O in the top left
rspec ./spec/display_board_spec.rb:61 # #display_board in 'lib/display_board.rb various game situations prints a board with X winning via the top row
rspec ./spec/display_board_spec.rb:73 # #display_board in 'lib/display_board.rb various game situations prints a board with O winning via the bottom row
rspec ./spec/display_board_spec.rb:85 # #display_board in 'lib/display_board.rb various game situations prints a board with X winning in a top left to bottom right diagonal
rspec ./spec/display_board_spec.rb:97 # #display_board in 'lib/display_board.rb various game situations prints a board with O winning in a top right to bottom left diagonal
rspec ./spec/display_board_spec.rb:109 # #display_board in 'lib/display_board.rb various game situations prints arbitrary arrangements of the board

```

VS:

`learn --fail-fast`
```
[23:24:16] (master) ttt-4-display_board
// ♥ learn --fail-fast

#display_board in 'lib/display_board.rb
  accepts a board as an argument
  various game situations
    prints a blank board when the board array is empty (FAILED - 1)

Failures:

  1) #display_board in 'lib/display_board.rb various game situations prints a blank board when the board array is empty
     Failure/Error: output = capture_puts{ display_board(board) }
     NoMethodError:
       undefined method `display_board' for #<RSpec::ExampleGroups::DisplayBoardInLibDisplayBoardRb::VariousGameSituations:0x007f9d04a6b9d8>
     # ./spec/display_board_spec.rb:11:in `block (4 levels) in <top (required)>'
     # ./spec/spec_helper.rb:5:in `capture_puts'
     # ./spec/display_board_spec.rb:11:in `block (3 levels) in <top (required)>'

Finished in 0.00126 seconds (files took 0.1164 seconds to load)
2 examples, 1 failure

Failed examples:

rspec ./spec/display_board_spec.rb:8 # #display_board in 'lib/display_board.rb various game situations prints a blank board when the board array is empty

```

## Bonus: Write Your Own Tests!

If you open `spec/display_board_spec.rb` in Sublime you'll see the test suite for this lesson. We left the last two tests pending. Read the instructions in the file and see if you can implement those tests.
