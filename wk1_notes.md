# Ada Week 1 Notes #

* [Get to Know Your Text Editor](#get-to-know-your-text-editor)
* [Core Object Types](#core-object-types)
* [Iteration and Blocks](#iteration-and-blocks)
* [Comparisons and Flow Control](#comparisons-and-flow-control)

### Get to know your text editor ###

* ⌘⇧p: Open the Command Palette to execute commands in the editor
* ⌘t: Search files, open in a new tab
* ⌘w: Close the current tab
* ⌘⇧w: Close the current window (all tabs)
* ⌘l: Select the current line
* ⌘⇧d: Copy the current line
* ⌃⇧k: Delete the current line
* ⌘^up & ⌘^down: Move the active line up or down
* ⌘d: Select the next instance of the highlighted string
* ⌃⇧up & ⌃⇧down: add a cursor in the same position on the line above/below. Press esc to get back to a single cursor.
* Auto Indent - Edit/Lines/Auto-Indent

### Ruby 102 ###

#### Core Object Types ####
* *_String_*: Created by enclosing characters between quotes. Access methods for strings with either dot notation or operator notation (i.e, .reverse or +). Can also use string interpolation using the #{}.

  Strings created from single or double quotes are identical in almost every way. The core difference is that double-quoted strings interpolate special characters and Ruby code. Single-quoted strings do not. For example \n is a special character for a new line. Using double quotes tells Ruby to evaluate this character. With single quotes, \n is not intepreted as a new line.

  * *_Symbol_*: Symbols are a lot like strings but represent identifiers. It is started with a colon (example: :elephant). The .object_id for symbols are always the same, whereas it differs for strings. This is because Ruby identifies a symbol as something to store for later use, where with strings every time the string is called a brand new String object is created. This is useful for Hashes. Use Symbols for things you want to come back for.

  * *_Integer & Float_*: Doing math with two Integers will return an Integer, and doing math with a Float will return a Float. It only takes on Float to return a Float.

  * *_Array_*: An array is an _ordered_ collection, containing 0 - however many objects. Arrays keep elements in order, and so are good to use when the order in which the elements appear is important. Each item in the Array corresponds to an integer value denoting its place, which makes Arrays _indexed_. Index always start at 0. If you create an array with one element but don't specify the element, it will be filled with Nil. When adding elements to an array, .push can add multiple elements whereas the shovel << can only add one element at a time.

  * *_Hash_*: Hashes are like dictionaries, there are words and then there are definitions of the words. With hashes, there are keys, and then there are values associated with the key. You access the values based on the keys. There are two syntax ways to form a hash. When the keys are in string forms, use the hackrocket to assign it a value (=>). The other option is symbol notation, which is the preferred notation for rubyists. Refer to symbol for why it is preferred. When using symbol notation the colon is after the word when forming the key, and before when referring to said key (pets: 2 when making, :pets when referring). Two important methods:  .keys gives you an array of the keys, .values gives you an array of the values associated with the keys. However values are not very useful without the key.

  * *_Nil_*: Nil is a special object of NilClass and represents "nothing". Used when a variable has not been assigned a value, or when methods don't or can't return a value.

  #### Iteration and Blocks ####

  _Iteration_ is the process of systematically interacting with a collection of values, one at a time.

  With a _times_ loop, the iteration starts at 0 and increments through each time it goes through the loop. With 10.times { |n| puts n }, for example, n will start at 0 and go through to 9.

  The _.each_ method is the most commonly used iteration method in ruby. It iterates through a collection such as an array.

  When making a block of code, use { } when the code is contained to one line, and do/end when the code is over one line.

  The _range_ iterator allows you to specify a starting and ending point for an iteration. It is not an array, but you can use .to_a to convert it into an array. There are _inclusive_ ranges, made with two dots (5..10), which will include 10. An _exclusive_ range is made with three dots (5...10), where 10 will not be excluded. You cannot create a range that goes backwards.

  Counter Controlled loops are when the computer knows the number of iterations that are going to happen in advanced. Sentinel control iteration is dependent on the array that or data structure that is being iterated through, and therefore the computer does not know ahead of time how many times the iteration will go through.

  #### Comparisons and Flow Control ####

  [Link to Lesson](https://github.com/Ada-Developers-Academy/textbook-curriculum/blob/master/01-ruby-fundamentals/04-comparisons-and-flow-control.md)

  Equality comparisons can be used on all object types
  * == equal to?
  * != not equal to?

  Numeric comparisons are used primarily on Integer and Floats
  * > greater than?
  * < less than?
  * >= greater than or equal to?
  * <= less than or equal to?

  Be careful using == with float numbers as the rounding might be slightly different.

  Conditionals allow control of the _flow_ of a program. They allow control over which blocks of code will execute.

  _if else_ is a common flow control conditional, but you can also use _unless_ which is an inverted if else (executes if false instead of true). Another way to do this is to use _negation_ by using the ! (not) operator. For example:
  * if !(conditional)
  * if variable != other variable

  #### Compound and Complex Conditionals ####

  Comparisons can be combined with && (and) and || (or). With And, both statements have to be true in order for it to result in True. With Or, only one statement has to be true for it to result in True.

  Ruby evaluates expressions based on precedence of operations.

  Precedence List from highest to lowest precedence.


  1. !, unary +
  2. **
  3. unary -
  4. *, /, %
  5. +, -
  6. * >, >=, <, <=
  7. * <=>, ==, ===
  8. * &&
  9. * ||

  Unary means assigning a numeric value as either positive or negative. (-5, -3, 7)

  Elsif will extend an if/else statement. If the if/elsif/else staement gets very long or has a lot of conditions you can use the case/when syntax.

  ```
  case command
  when "add", "+"
  puts "We're adding numbers"
  when "subtract", "-"
  puts "We're subtracting numbers"
  when "sqrt"
  puts "We're finding the square root of a number"
  else
  puts "What do you want from me?!"
  end
  ```
  Here "," represents or. Case statements only work when it deals with only one variable, in this case command.

  while and until are loop structures. While runs until a condition is true, while until runs until a condition is reached.

#### Methods ####

Creating methods allow us to assign a _name_ and _structure_ to sections of code. We create methods when we want code that is going to be reused and execute independent of the code that surrounds it.

A method has a _method signature_. A method signature is comprised of 2 parts: the *name* of the method, and the *arguments* it is expecting.

To use a method you have to call it. You call a method by using the method name followed by any parameters in parenthesis. The paramrter is passed into the method as an argument. It is ideal to make the method before calling it.
