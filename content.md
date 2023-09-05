# Summer '23 Day 3 notes

## Put your code in blocks on Ask

We're very happy to see all of the activity on Ask! But please do us a favor when writing a post:

1. Include your code, and include any error messages.
1. When copy-pasting code or errors, place them within [fenced code blocks](https://gist.github.com/raghubetina/a1b6e89e24a8c3acae6f0b63a1fd3323#code-blocks):

In other words, rather than:

```txt
My code isn't working!

<a href="wikipedia.org">Go to Wikipedia</a>
```

Please use:

    My code isn't working!
    
    ```
    <a href="wikipedia.org">Go to Wikipedia</a>
    ```

You can also optionally include the language after the opening backticks, for nicer syntax highlighting:

    My code isn't working!
    
    ```html
    <a href="wikipedia.org">Go to Wikipedia</a>
    ```

It is especially important to use fenced code blocks when pasting long chunks of code or error messages. Without them, we lose all indentation and formatting and the code becomes very hard to read.

## Use GP-TA as a spotter, not a spoiler

Imagine you buy a gym membership because you want to get stronger. Then, you get a robot to come with you to the gym and lift all the weights on your behalf. Seems a bit counterproductive, no?

Beware of doing that to yourself with GP-TA. Use it as a spotter, not a spoiler.

I find it to be a great brainstorming aid, but make sure you're trying to understand what it's telling you (not least because it's completely wrong sometimes, so blindly following its advice can be counterproductive). Ask it follow up questions to clarify your understanding — that's what makes it great!

Ultimately, rely on your human instructors for authoritative answers. We're working on giving you a way to escalate to a human instructor with a click, but in the meantime, reply to your thread asking for an instructor to take a look and we'll all get notified.

Thank you!

## How to write and run a "real" Ruby program

The runnable code blocks within lessons here are nice because they allow us to dive right into experimenting with Ruby expressions.

But, to write real programs, we need to be able to write files that can be thousands of lines longs. Here within a code block, it's already annoying to scroll up and down when a program gets longer than 10 lines!

Even more importantly, we need to be able to create _multiple_ files that all collaborate together when executing the program. And, we need to pull in gems — code written by other people that we want to use.

For all these reasons and a bunch more, we need to start using a real environment to write our Ruby program. Codespaces to the rescue!

Please go back to Canvas and find the lesson called "Running real Ruby programs" under the _Intro to Ruby_ module. We'll go follow those notes together now, before returning here.

## The many ways of printing

So far, we've been using Ruby's built-in `pp` (pretty print) method for all of our printing. But there are a few other printing methods that you will encounter, so let's chat about them:

### Put string (`puts`)

Try the following:

```ruby
x = "Howdy!"

pp x

puts x
```
{: .repl #puts_1 title="puts, 1" points="1"}

Can you spot the difference?

Try this one:

```ruby
x = [4, 8, 15, 16, 23, 42]

pp x

puts x
```
{: .repl #puts_2 title="puts, 2" points="1"}

This time it's easier to spot the difference.

The `pp` methods shows an object in all of its gory, technical detail; which is what we usually want, because we're usually printing in order to debug our code.

Behind the scenes, `pp` calls a method `.inspect` on whatever object you give it. `.inspect` can be called on any object, and returns a `String` with additional information about the object. Then, `pp` displays that string.

But sometimes you are writing a program for other people's consumption, and you don't want to show the double-quotes around strings, etc. You want the output to look nice and clean for the end user.

For those times, the `puts` method (pronounced "put string" or "put S") is your friend.

Behind the scenes, `puts` calls a method `.to_s` on whatever object you give it. `.to_s` can be called on any object, and returns a _user-friendly, formatted_ `String`  representing the object. Then, `puts` displays that string.

Either way, both `puts` and `pp` are doing some extra work on the object — `.to_s` and `.inspect`, respectively — to convert the object into a `String` that's ready for printing. `puts` uses `to_s` in order to get a string that's nicely formatted for an end user, and `pp` uses `.inspect` in order to get a string that contains the gory technical details for a developer.

Notice in this example:

```ruby
x = [4, 8, 15, 16, 23, 42]

puts x
```
{: .repl #puts_3 title="puts, 3" points="1"}

`puts` is doing a lot of work for us! It converts each element of the array into a `String`, then it prints each of those on its own line. But, just by looking the output of `puts`, a developer couldn't immediately tell where those five strings came from. Maybe they were each individual variables? Who knows?

With `pp`, it's much easier to understand what `x` actually _is_:

```ruby
x = [4, 8, 15, 16, 23, 42]

pp x
```
{: .repl #puts_4 title="puts, 4" points="1"}

Like I said, since I'm almost always printing in order to **make the invisible visible** to help myself debug, I almost always use `pp`. But sometimes `puts` comes in handy.

## Ruby Gym

Now that we've expanded the tooling at your disposal, we're going to spend a bunch of time building simple yet substantive Ruby programs. We call it the Ruby Gym — it's your chance to get in some reps before we start applying the fundamentals to solve real, valuable problems.

First, you should make sure that you're caught up on the _Intro to Ruby_ module. If you haven't gotten at least as far as "The Hash class", then there's no point attempting the Ruby Gym. Spend time catching up, and ask the instructors lots of questions.

Then, take a look at the Codecademy: Learn Ruby assignment. Sometimes it's worth hearing the same information in different words. If you're feeling shaky on foundational concepts like variables, conditionals, and loops, then consider going through Codecademy's Ruby intro next.

Finally, find the Ruby Gym module in Canvas, open the first assignment ("Ruby conclusions and gym"), read the instructions, and keep going. I will demonstrate the first one now, and then we'll split up into breakout rooms to work on whatever makes most sense for where you're at.

Please remember that you can summon an instructor into your breakout room by clicking the "Ask Question" button in the Zoom toolbar. **We're just waiting** for you to ask us something, anything! (And please feel free to share screen and collaborate with each other in your breakout rooms, too.)

Please take this time to catch your breath and catch up on Ruby, with our help. That concludes the presentation for today.

