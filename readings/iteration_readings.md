# Iteration

### What is iteration?

Abstractly, programming is all about automating chunks of repeatable work.

Say we wanted to write a method that took a name and printed it a certain number of times. Without iteration, we'd have to call that method manually to reach our print quota.

```ruby
def print_name(name)
    p name
end

# if we wanted to print it five times
print_name("michael")
print_name("michael")
print_name("michael")
print_name("michael")
print_name("michael")
```

That's horrendously inefficient. Just imagine how much worse that'd be if we wanted to print a name 100 or 1000000 times.

Luckily, Ruby makes iteration--the execution of repeatable chunks of work--incredibly intuitive and fun to use.

```ruby
def print_name(name, print_quota)
    print_quota.times do |i|
        p name
    end
end

print_name("michael", 5)
print_name("michael", 5000000000)
```

Our `print_name` method is now compact and reusable--a hallmark of good programming.

Let's unpack what's happening in the method above. `print_name` takes two arguments, a `name` to print and a number, `print_quota`, of times to print it.

The Integer class in Ruby comes with a method called `times` (more detail [here](http://www.ruby-doc.org/core-2.1.1/Integer.html#method-i-times)).

`times` will execute a given snippet of code as many times as we specify. This snippet of code is called a block, but don't worry about that just yet. We specify that snippet with the following structure:

```ruby
do |arbitrary_variable_name|
    # code goes here
end
```

In effect, we're creating a miniature, nameless method inside another method. We then execute this mini-method repeatedly. In the case above, we're using that code snippet to print a passed-in name.

Iteration, clearly, is quite powerful.

### Simple versus complex iteration

### Conditional iteration

### Finite versus infinite loops

### The magic of Enumerable

### Blocks in detail

### Procs

### Lambdas

### Style guidelines

### Required readings

* Alan Skorkin on [Ruby Loops and Iterators](http://www.skorks.com/2009/09/a-wealth-of-ruby-loops-and-iterators/)
