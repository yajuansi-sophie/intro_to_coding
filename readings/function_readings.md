# Functions & Methods

### What is a function?

Functions (more frequently called **methods**) do three things:
1. Take input (called arguments)
2. Perform work on the inputs
3. Return something, the output of the function

### Creating a function

Say we wanted to write a function that would print "Hello!". In Ruby, that might look like this:

```ruby
def print_hello
  puts "Hello!"
end
```

Clearly, a function that performs the same thing every time doesn't need to take any input. The input is implicit.

To create a function, use the `def` keyword followed by a name for the function (`print_hello` in the above example), the arguments that the function expects (none in this case), and the `end` keyword.

What happens in between is up to the requirements of the program.

### Taking arguments

Alternatively, what if we wanted to print someone's name? Maybe our function would look like so:

```ruby
def print_name(name_to_print)
  puts name_to_print
end
```

Ruby convention is to declare your arguments in parentheses right after the method name.

### Returning values

Every function returns a value. In Ruby, the last value computed in a function is implicitly the return value unless you explicitly specify otherwise using `return`.

Let's look at a really contrived example:

```ruby
def multiply_by_two_after_saying_hello(number_to_multiply)
  puts "Hello!"

  return number_to_multiply * 2

  puts "We're never going to get here!"
end
```

Because we explicitly return (i.e. exit the function with the passed-in argument), the function never gets to print out the final statement.

This will be come in handy later on when we want to handle bad inputs (but don't worry about that yet).

### Calling a function

Say we have a function like called `multiply_by_two`:

```ruby
def multiply_by_two(number_to_multiply)
  return number_to_multiply * 2
end
```

We call (i.e. use) this function like so:

```ruby
multiply_by_two(2) # => 4
multiply_by_two(4) # => 8
multiply_by_two(3) # => 6
```

Now we can easily reuse our function over and over again--one of the main benefits of programming!

### Default argument values

It's usually a good idea to program defensively--anticipate where users of your program might mess it up, and prevent them from doing so.

Default argument values go a long way towards helping you do that.

We could rewrite the above function `print_name` to take a default value like so:

```ruby
def print_name(name_to_print = "Anonymous")
  puts name_to_print
end
```

If we specify a value for that argument when we call the function, our passed-in value is used. Otherwise, the default value is invoked.

```ruby
print_name("Michael") # => "Michael"
print_name("David") # => "David"
print_name() # => "Anonymous"
```

### Chaining methods

Methods can be chained together, like so:

```ruby
"a string".capitalize.reverse # => "gnirts A"
```

The return value of the first method, `capitalize`, gets passed to the second method, `reverse`.

Obviously, this will make your code concise. Beware, though, of chaining too many methods together (especially unrelated methods).

Once you start converting and mixing types (i.e. `strings` with `integers`), you're on shaky ground. More than a few chained methods is usually a bad idea.

### Proper function size

There are entire books written on how to name and structure functions. As you become a more experienced programmer, you'll surely stumble upon these.

Until then, here's the rule: write as little as possible necessary to let your function tell a story. After all, the code you write needs to be readable by whoever happens upon it later.

Applied to our functions above, we don't need them to calculate Pi to thousands of digits--it's very clear what each function is supposed to do, and neither does anything unnecessary. The story is clear.

A program is usually better when composed of several small, easily-understandable functions (which encapsulate logical chunks). Monolothic functions are almost always a terrible idea.

When it doubt, cut it out.

### Required readings

* [Chapter 18](http://ruby.learncodethehardway.org/book/ex18.html)
 and [Chapter 19](http://ruby.learncodethehardway.org/book/ex19.html) from Learn Ruby the Hard Way
* [This Wikipedia article](https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Method_Calls), a comprehensive introduction to Ruby methods
