# Control Flow Exercises

### Capitalization

Write a method `name_case_shifter` that takes a string input.

If that input is your name, you should capitalize every letter. Otherwise, every letter should be lowercase.

Hint: you'll want to check out the `upcase` and `downcase` methods.

### Min and Max

Write a method that takes two number inputs and compares them.

Print the difference and return whether one is greater than, less than, or equal to the other.

### Include?

Write a method `input_checker` that takes a string as an input.

You should check to see if the input has either has the words "ran" or "rest", or both. Return something that denotes the condition satisfied.

You'll want to use the `String.include?` method.


### Mini-Fizz-Buzz

Write a method `fizz_buzzer` that takes an input and checks for four things
* It is divisible by 3, in which case print "Fizz"
* It is divisible by 5, in which case print "Buzz"
* It is divisible by 3 and 5, in which case print "FizzBuzz"
* It is divisible by neither, in which case print the number

To check for divisibility, you'll need to use the modulo operator, `%`.

The modulo operator attempts to divide the left element by the right element, and returns the remainder to you. Contrast this with the division operator, `/`, which returns the number of times one number is divisible by another.

Here are some examples illuminating the difference.

```ruby
24 / 6 # => 4
24 % 6 # => 0
26 / 6 # => 4
26 % 6 # => 2
```
