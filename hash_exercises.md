Hashes
======

### collected_works

Your literature buff friend wants to catalogue the writings of her favorite authors. Let's help her out.

Write a function that takes an author and a title and adds it to the collected works for that given author. You should definitely create a hash that will keep track of the collected works of all your authors. If that author doesn't have a record already, create one and add the book title to that author. 

### make_change

Unfortunately, the cash register at your local breakfast spot is out of commission, and the employees are backed up while they try to calculate everybody's change.

Your function `make_change` should take an amount and calculate the number of dollars, quarters, dimes, nickels, and pennies to return for that amount. Do this with a hash rather than some alternative data structure.

Calling `make_change(17.89)` should return something like the following:
    {
        "dollars" => 17,
        "quarters" => 2,
        "dimes" => 3,
        "nickels" => 1,
        "pennies" => 4
    }

Hint: for this problem, you'll need to know the difference between the modulo operator and division:

    10 / 3 # => 3
    10 % 3 # => 1
### vote_counter

You've been tasked with counting votes in an upcoming election.

Write a function that increments the vote count by a given amount for a given politician. 

Next, write a function that prints out the results of the election in the format `candidate: vote_count` for each candidate.

Hint: if your `vote_count` is an Fixnum object type (it probably is), you might have to use the [`to_s`](http://www.ruby-doc.org/core-2.1.0/Fixnum.html#method-i-to_s) method to be able to print it out.

### hash_unscrambler

Unfortunately, the military alphabet is all scrambled. Instead of an orderly code, our soldiers got the instructions `{"a" => "bravo", "b" => "charlie", c => "alpha", "d" => "delta"}`. Note that not all letters are scrambled.

Your job is to unscramble this alphabet and return an orderly code. You'll probably want to write multiple functions to do this, although you could certainly do it in just one.