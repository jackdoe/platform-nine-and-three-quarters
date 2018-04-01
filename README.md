it is not easy
---
![well](well.jpg)

this is not really a tutorial, just trying to relate very basic language constructs to programming,
so it will feel a bit like the picture above, but fear not, after grinding for a while you will draw a panda.

---
## if

    If you eat your meal, you can have icecream for desert.

doesnt seem difficult, and it translates to something like


    if (daughter eats her meal)
        she can have icecream
    else
        no icecream
    end

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

## objects
