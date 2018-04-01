it is not easy
---
![well](well.jpg)

I am writing this for my wife Gergana and I am trying to make it
useful for her, so I am perfectly fine if you (who is reading this tutorial and
is not Gergana) do not like it.

This is not really a tutorial, just trying to relate very basic language constructs to programming,
so it will feel a bit like the picture above, but fear not, after grinding for a while you will draw a panda.

I promise you if you master only 4 things you will be able to climb the learning curve.

Keep in mind that the learning curve is not really a curve, but rather
a learning staircase, once you learn a concept it does not get easy right away, but after quite some tinkering.

The four things you have to master are:

* understand the meaning of the word 'if'
* repetition (or looping)
* variables
* goto

This now sounds very abstract and useless, but by the end of the
course you will be able to write some useful programs.

* fun math game for Bella
* trip budget planner
* tick tack toe game
* app that keeps track of how long Bella plays on the iPad
* dog walk calendar
* food tracking app


At first we will start by understanding the very basic concepts, and
then you will have to memorize some syntax, which will seem like magic
spells, and this is fine.

Our goal is to replace most of the magic incantations with physics
understanding, in general the way new concepts will be introduced are
magic first - physics later.

For example when Bella asks me why do soap bubbles have colorful
rings, I simply tell her: because of light, when you grow up you will
have to spend some time figuring it out; instead of trying to explain
quantum interference.


The most important thing is to not give up and understand that it is
simply difficult and it is difficult to anybody who is just starting.

It might also help you to translate this text to Dutch, I think this
will help you to memorize the incantations better.

There are hundreds of books, each is trying to teach from different
approach, but I belive this is the best way for you, so sit back,
relax and try to not close the laptop in despair.

---

# foundation

## if

    If you eat your meal, you can have icecream for desert.

doesnt seem difficult, and it translates to something like


    if (Bella eats her meal)
        she can have icecream
    else
        no icecream
    end


another example:

    If it is not raining, we will go to the sea

code:

    if (not raining)
        go to sea
    else
        stay at home
    end

read it again **until** you can come up with at least 5 examples,
write the examples in the format:

    sentence in english
    code

send me the examples to my email (jack@sofialondonmoskva.com)

there is a lot of syntax involved here, so lets break it down

    if [something that is either true or false]
        code block executed if it is true
        the code block can be multiple lines
    else
        code executed if it is false
        this code block can also be multiple lines
    end

there are many ways to declare a code block some examples:


    if (not raining) {
       go to sea
    } else {
       stay at home
    }

or

    if not raining:
       go to sea
    else:
       stay at home

And there are many more, so when you read code you have to learn to just look for the `code blocks` doesnt matter if the language you are reading has brackets or spaces or semicolons or square brackets etc.

The point I am trying to make is that it is very easy to get scared when you look at any example code because it is full of weird symbols, for example:

    if (!raining) {
       go_to_sea();
    } else {
       stay_at_home();
    }

whoooaa, what is going on, so many symbols, there is `! () { } ; and _` so you will have to remember what they mean.

**!** means `not` literally `!raining` means `not raining`, `()` are used to
group the if condition, and `{}` are defining the code block, `;` is
saying somewhat equivalent to "end of sentence"

Anyway dont get too scared of symbols, we will get back to them later

Keep in mind that syntax is absolutely irrelevant the point is in the `condition` and `code block`



## loops

    you can not play outside, until you finish your homework

same as

    until homework finished
        no play
    end
    let her play outside

or

    while not (homework finished)
        no play
    end
    let her play outside


another example is right in the previous section:

    read it again **until** you can come up with at least 5 examples,

    until (you can think of 5 examples)
        read the #if section
    end
    read the next section


## infinite loops

while(or until) loop syntax is `while [condition is true]`, so we can simply do `while 1 == 1`, or `while true`

## breaking out of the loop

    you can play outside after 4 o'clock

so of course she will be super excited and just watch the clock all the time, so this will translate to

    while true
        if clock == 4pm
            break out of the loop
        end
    end

    play outside :)


## variables

    lets flip a coin to decide which pizza to order, heads is dominos and tails is newyorkpizza

variables are simply placeholders, their name is irrelevant, we only care about their value

    order_from = dont know yet
    coin_result = flip coin
    if (coin_result == heads)
        order_from = dominos
    else
        order_from = newyorkpizza
    end

in this example we used 2 variables `order_from` and `coin_result`, in coin_result we simply hold the vaule of the actual coin flip

you can think of a variable as a `box` with a label, the label of the box is the **name** of the variable, the content of the box is its **value**


## variables with loops

now this is very of cool

    with this shampoo you have to wash your hair 5 times, each time put shamoo, wait 3 minutes and rince

so using variables and loops we can do

    number_of_times = 0
    while number_of_times < 5

        put shampoo
        wait 3 minutes
        rince

        number_of_times = number_of_times + 1
    end
    get out of the bathroom

the computer executes that as follow

    set number_of_times to 0
    LOOP: is number_of_times < 5
    if yes
        put shampoo
        wait 3 minutes
        rince

        number_of_times = number_of_times + 1
        goto LOOP
    end

    get out of the bathroom
        
so you can see just as it is about to continue with the program we `goto` the loop beginning and check if the condition is still valid


in many languages there is syntactic suggar for this kind of loops, called `for` loop, and for `x = x + 1`, called incrementing a variable, to be written as `x++`

the syntax is something like:

    for [initial configuration]; [while condition is true]; [do this on each iteration]

in our case this looks like:

    for number_of_items = 0; number_of_items < 5; number_of_items++
        put shampoo
        wait 3 minutes
        rince
    end
    get out of the bathroom

well.. in most language each of the `for` parameters is optional :) so you can have

    number_of_items = 0
    for ; number_of_items < 5; number_of_items++
        put shampoo
        wait 3 minutes
        rince
    end
    get out of the bathroom

or

    number_of_items = 0
    for ; number_of_items < 5 ;
        put shampoo
        wait 3 minutes
        rince
        number_of_items++
    end
    get out of the bathroom

wait.. this looks the same as the while loop; yes, yes it does.

we can also use inifinite loop and break out of it

    number_of_items = 0
    for ;; [same as while 1=1, or while true]
        put shampoo
        wait 3 minutes
        rince
        number_of_items++
        if (number_of_items >= 5)
            break from the loop
        end
    end
    get out of the bathroom

now.. to the core of all cores, the basic of all basics:

# loops are just syntactic suggar for `if` and `goto`
    
    number_of_items = 0
    LOOP: if (number_of_items < 5)
            put shampoo
            wait 3 minutes
            rince

            number_of_items++
            goto LOOP
          end

    get out of the bathroom

if you can get past this point, you can be called a programmer

## functions

## recursion

## bytes

## integers

## strings

## arrays

## maps

## messages

## objects

## input/output

## build our first useful program

## html

## javascript

## git

## build our second app

## machine code

## harvard vs von neumann

## c

## virtual machines

## http

## make js + html communicate with c web server

## sort

## search

## hashing

## make our first database

## mysql

## make our first complex webapp

## distributed computing

## next steps
