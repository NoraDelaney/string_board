### README

Run `ruby string_board_challenge.rb` at the command-line with a string of 1s and 0s as a parameter.

A few edge cases:
* Valid board sizes.
Because the board cannot be one column long or one row wide, I initialized `x` (which corresponds to row length) to `2` and I ensured that `x` remained less than the string's total length as I incremented `x` in the following snippet of code:
```
x = 2
x_array = []
while x < string.length
  if string.length % x == 0
    x_array << x
  end
  x += 1
end
```

* Ties
To determine the board with the maximum length, I summed the number of solid columns and number of solid rows in each board, creating a `sum_array` array. I determined whether there was a tie (more than one board with the maximum sum of solid rows and/or columns) with the following snippet of code:

```
if sum_array.count(sum_array.max) > 1
  puts "We have a tie!"
  puts "Boards with most solid rows and columns:"
  puts
  sum_array.length.times do |i|
    if sum_array[i] == sum_array.max
      puts array_of_rects[i].map(&:join)
      puts
    end
  end
  ...
end
```

I did not keep track of the time I spent on the challenge, but I would guess it was roughly 4 or 5 hours.

A bit of background about me: I recently completed an apprenticeship in web development (primarily Ruby on Rails, with some Javascript) at Launch Academy and am seeking a role as a junior developer.
