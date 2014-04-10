# Control Flow

### Conditional logic

Usually, your methods will to respond to different types of inputs. Maybe a method `translate_word` does different things depending on the arguments `from_language` or `to_language` that you provide.

Handling such inputs conditionally will inform a lot of the way you write your code.

Thankfully, Ruby has a pretty robust toolbox for implementing that logic.

### Comparisons in Ruby

Comparing two objects in Ruby returns a boolean value--either `true` or `false`.

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
    if number_to_compare <= 5
        return "Your number is less than or equal to 5!"
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

You'll come across case statements, which logically are very similar to the if-else construction above.

Let's take a look at `compare_to_5` if it were implemented using a case statement.

```ruby
def compare_to_5(number_to_compare)
    case number_to_compare <= 5
    when true
        return "Your number is less than or equal to 5!"
    when false
        return "Your number is greater than 5!"
    else
        return "Weird input alert!"
    end
end
```

You provide the case statement with something to evaluate. Based on the result of that evaluation, it will execute the code you specify. Nifty!

Here's another example:

```ruby
def print_something(input)
    case input
    when true
        return "This will always return!"
    when false
        return "This will never return!"
    end
end
```

Unless we explicity call `print_something(false)` or `print_something(nil)`, our method will always spit back "This will always return!"

How is this the case when we don't provide a full statement to evaluate? Welcome to truthiness and falsiness.

### Truthiness and falsiness in Ruby

In Ruby, everything has a "truthiness" property, which can either be "truthy" or "falsey".

By virtue of its existence somewhere in memory, everything in Ruby is truthy, except for two values: `false` and `nil`.

What does this mean? Basically, everything in Ruby has an implicit boolean assigned to it. Most of the time, that implicit boolean is `true`, although in two cases it is `false`.

This lets us do some fancy stuff with regards to control flow. Let's dive into more detail.

```ruby
def truthiness_opposite_printer(input)
    # will print the inverse of an object's truthiness
    puts !input
end

truthiness_opposite_printer(1) # => false
truthiness_opposite_printer("hello") # => false
truthiness_opposite_printer(false) # => true
truthiness_opposite_printer(nil) # => true
```

Remember: everything in Ruby is truthy except for `nil` and `false`. We ask for the boolean inverse of this state. A truthy object's boolean inverse is `false`, and conversely a falsey object's boolean inverse is `true`.

Let's look at how we might apply that to control flow:

```ruby
def conditional_printer(input)
    if !input
        # this means input was falsey
        # do nothing
        return
    end

    puts input
end
```
In the above example, we only print the input if it is a truthy value. The falsiness of a `nil` or `false` would be converted to a `true`, which would trigger an early exit from our method.

There is an easier way, however, to express that logic:

```ruby
def conditional_printer(input)
    unless !input
        puts input
    end
end
```

Remember `unless`? The code within an `unless` always gets executed unless the condition evaluates to true. The method above will always get executed unless `input` is `false` or `nil`, whose falsiness gets converted into a `true`.

Now, let's get a little crazy:

```ruby
def truthiness_boolean_value_printer(input)
    # this prints the inverse of inverse of an object's truthiness
    puts !!input
end

truthiness_opposite_printer(1) # => true
truthiness_opposite_printer("hello") # => true
truthiness_opposite_printer(false) # => false
truthiness_opposite_printer(nil) # => false
```

Let's rewrite the ugly `conditional_printer` method above, this time using our friends `if` and `!!`:

```ruby
def conditional_printer(input)
    # this will only execute if input is a truthy value
    if !!input
        puts input
    end
end
```

Understanding how truthiness and falsiness works in Ruby will go a long way to helping you express yourself concisely.

### && and | |

What if you want to chain different statements together? Maybe I have a crazy method like the following:

```ruby
def print_if_name_is_michael_and_seven_letters(name)
    if name == "michael"
        puts name
    end

    # the length method returns the number of characters in a string
    if name.length == 7
        puts name
    end
end

# all of these will print
print_if_name_is_michael_and_seven_letters("michael")
print_if_name_is_michael_and_seven_letters("rebecca")
print_if_name_is_michael_and_seven_letters("asjhdf;")
```

We need a way to chain multiple conditions together for the above method to work as intended. Thankfully, `&&` exists.

```ruby
def print_if_name_is_michael_and_seven_letters(name)
    if name == "michael" && name.length == 7
        puts name
    end
end

# this will print
print_if_name_is_michael_and_seven_letters("michael")
# these won't print
print_if_name_is_michael_and_seven_letters("rebecca")
print_if_name_is_michael_and_seven_letters("asjhdf;")
```

What if we wanted to execute some code if any single one of a group of conditions either resulted in true or resulted in false? `| |` gets that job done for us.

```ruby
def print_if_name_is_michael(name)
    if name == "michael" || name == "Michael"
        puts name
    end
end
```

Now, you can chain multiple statements together to your heart's content.

### Logic tables

Check out [Chapter 27](http://ruby.learncodethehardway.org/book/ex27.html) in Learn Ruby the Hard Way.

Initially, you'll want to check back to these truth tables frequently to make sure you are getting the logic of your programs down pat. Eventually, it'll become second nature.

### Tightening the syntax

Ruby is remarkably expressive and does its best to let you structure your code in a readable way.

One way to make your control flow look a little cleaner is to one-line your conditions:

```ruby
def print_name(name)
    puts name if !!name
end
```

An example using `unless`:

```ruby
def print_name(name)
    puts name unless name.length > 7
end
```

Always one-line your conditional statements if there is only one condition. Otherwise, break it out into a larger `if`/`else` statement.

### Required Reading

* [Chapter 29](http://ruby.learncodethehardway.org/book/ex29.html) and [Chapter 30](http://ruby.learncodethehardway.org/book/ex30.html) of Learn Ruby the Hard Way
* Codecademy's lesson on [Ruby Control Flow](http://www.codecademy.com/courses/ruby-beginner-en-NFCZ7/0/1)
* Avdi Grimm on [&& and || in Ruby](http://devblog.avdi.org/2010/08/02/using-and-and-or-in-ruby/)
