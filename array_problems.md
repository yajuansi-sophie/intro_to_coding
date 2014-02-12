Arrays
======

# my_uniq

Arrays have a method `uniq` which returns all the unique elements within a given array. We're going to implement our own version of that.

	my_uniq([1, 2, 3, 3, 4, 5, 5]) # => [1, 2, 3, 4, 5]

You might find the [`.include?`](http://ruby-doc.org/core-1.9.3/Array.html#method-i-include-3F) method useful.

# two_sum

Write a function that takes an array of numbers and returns an array of positions where the elements at those positions sum to zero.

	two_sum([-1, 0, 2, -2, 1]) # => [[0, 4], [2, 3]]

The positions should correspond to [smaller_index, larger_index], which is to say `[[0, 4], [2, 3]]` rather than `[[4, 0], [3, 2]]`. This should be easily to accomplish if you are iterating through the array in a reasonable way.

# stock_picker

This function will take an array of stock prices (the index is the day). You'll iterate through the prices and find the buy date/sell date interval that produces the most profit.
	
	stock_picker([10, 20, 30, 5, 25, 40]) # => [3, 5]

You obviously don't want to compare a buy date with a sell date that happened in the past, so consider adding the line `next if (some_condition)` to skip that iteration if `some_condition` is met. Hint: this is a very similar problem to `two_sum`.

# my_transpose

We're going to take a matrix (a two-dimensional grid of numbers) and transpose it. Here's an example:

	my_transpose([
	    [0, 1, 2],
	    [3, 4, 5],
	    [6, 7, 8]
	  ])
	 # => [[0, 3, 6],
	 #     [1, 4, 7],
	 #     [2, 5, 8]]

This one's a little trickier than the other problems. Once you reach this, let me know so I can point you in the right direction.
