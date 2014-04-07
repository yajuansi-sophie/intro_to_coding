# Control Flow

### Conditional logic

Usually, your methods will to respond to different types of inputs. Maybe a method `translate_word` does different things depending on the arguments `from_language` or `to_language` that you provide.

Handling such inputs conditionally will inform a lot of the way you write your code.

Thankfully, Ruby has a pretty robust toolbox for implementing that logic.

### Comparisons in Ruby

Comparing two statements in Ruby returns a boolean value--either `true` or `false`.

There are a number of comparison operators in Ruby: `<` for less than, `>` for greater than, `<=` for less than or equals, `!=` for not equal to, `==` for equal to.

Let's look at some examples:

```ruby
# is 1 less than 2?
1 < 2 # => true
# is 1 greater than 2?
1 > 2 # => false
# is 1 less than or equal to 2?
1 <= 2 # => true
# is 1 greater than or equal to 2?
1 >= 2 # => false
# does 1 not equal 2?
1 != 2 # => true
# does 2 not equal 2?
2 != 2 # => false
# does 1 equal 2?
1 == 2 # => false
# does 2 equal 2?
2 == 2 # => true
```

See [this StackOverflow answer](https://stackoverflow.com/questions/7156955/whats-the-difference-between-equal-eql-and) for more about checking for equality.

### If, else, elsif

Ruby provides you with a few conditional evaluators to help you manage control flow.

Say we had a method `compare_to_5` that tests the passed-in value to see if it's greater than the number 5. Depending on whether it's greater than 5, less than 5, or equal to five, we should return something different.

```ruby
def compare_to_5(number_to_compare)
    if number_to_compare < 5
        return "Your number is less than 5!"
    elsif number_to_compare > 5
        return "Your number is greater than 5!"
    elsif number_to_compare == 5
        return "Your number is equal to 5!"
    else
        return "Weird input alert!"
    end
end
```

For each if/elsif statement, the "truthiness" or "falsiness" of the clause is determined. If the clause returns as "truthy", the subsequent code will execute.

What are truthiness and falsiness? We'll get to that in a second.

### Unless

Think of `unless` as the counterpart to `if`. Here's an example:

```ruby
def print_when_not_equal_to_5(number_to_compare)
    unless number_to_compare == 5
        return "Not equal to 5!"
    end

    return "Equal to 5!"
end

print_when_not_equal_to_5(500) # => "Not equal to 5!"
print_when_not_equal_to_5(5) # => "Equal to 5!"
```


### The case statement

### Truthiness and falsiness in Ruby

### && and | |

### Logic tables

### Tightening the syntax

### Required Reading

* [Chapter 27](http://ruby.learncodethehardway.org/book/ex27.html), [Chapter 29](http://ruby.learncodethehardway.org/book/ex29.html) and [Chapter 30](http://ruby.learncodethehardway.org/book/ex30.html) of Learn Ruby the Hard Way
* Codecademy's lesson on [Ruby Control Flow](http://www.codecademy.com/courses/ruby-beginner-en-NFCZ7/0/1)
* Avdi Grimm on [&& and || in Ruby](http://devblog.avdi.org/2010/08/02/using-and-and-or-in-ruby/)
