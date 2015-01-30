---
title:  "Day 5 - part 1: A thought to share!"
---

So, in the DinnerClub class we worked on this week, it looked like everyone (including the instructor examples) used the following in the members attribute to define that members is an array (or, you might have also defined it as a hash):

`@members = []`

or, you could also do:

`@members = Array.new`

Sumeet showed a couple of us another way to do this just using:

`@members = members`

This doesn't define this instance variable as an array, but instead allows you to define it when initializing the class. You initialize method would now include:

`def initialize(members)`

Now, when you run it you would do something like this:

dc1 = DinnerClub(["John", "Paul", "Ringo", "George"])

and this will now create members as an array.

You might then ask yourself **"What happens when someone initially only passes a single parameter?"** You can counter this by using "raise" to call an error if they try this:

```
class DinnerClub

  def initialize(total_bill, members)
    if !members.is_a(Array)
      raise "ERROR!"
    end
    @members = members
    @total_bill = total_bill
  end
end
```

Sumeet mentioned that you might gain more flexibility in your code if you aren't defining the instance variable from the get-go, but this is just another way to do what you want so I thought I would share it...