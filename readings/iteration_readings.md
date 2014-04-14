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

### Finite versus infinite loops

### Simple versus complex iteration

### Conditional iteration

### The magic of Enumerable

### Blocks

### Procs

### Lambdas

### Style guidelines

### Required readings

* Alan Skorkin on [Ruby Loops and Iterators](http://www.skorks.com/2009/09/a-wealth-of-ruby-loops-and-iterators/)
