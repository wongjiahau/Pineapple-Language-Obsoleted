The Pineapple Language
By: Wong Jia Hau
3 pillars of the design:
    1. Readability (easy to read)
        -verbose on main actor (e.g. function name should be as verbose as possible)
        -terse on calafe(e.g. if else, return, list statement should be 
                    as terse as possible as they are not the main point)
    2. Typability (easy to type, use as less SHIFT as possible)
    3. Learnability (easy to learn)
    4. Orderity (prevent bad coding practice) # is this even possible?

Current Rules:
	1. a class can only contain data, no methods allowed #because it's not necessary
	2. inheritance is allowed
	3. -caller must be written above callee, else result in compile error
	4. -every thing is passed by reference, if the function is mutating the input parameter,
	user will be warned at compile time
	5. -statement are evaluated from top to bottom (aka imperatively) 
	6. -pattern matching is supported
	7. -functions has higher precedence than operators
	    -all operators have the same precedence
	    -unary operator/function has higher precedence than binary operator/functions 
	8. -a standard commitee need to be form to standardize the libraries of this programming language 
	    e.g. because NOT operator is not a predefined one, so which operator should be defined as the NOT operator? 
	9. any data type have these attributes
	    -type
	10. unit test can be written easily
	

`keywords
    1. param1, param2, param3, ...
    2. error `a function that return this will raise compile error 
    3. nil, yes, no 
    4. break , continue
    
`atomic operators
`these operators cannot be defined anymore in high level statement
    `unoverloadable operator
        [ ] enclosure for function name
        ( ) enclosure for precedence
        { } enclosure for list or verbose variant for atomic operators
        = {store}, {as}
        $ char literal operator     
        ' ' string literal enclosure
        : {return} or {as}
        :: {as allias to}
        ... ellipses 
        . {'s} 
        " {of}
        \ grouping , dereferencor for group
        \\ enumeration operator
        | {such that it's}
        # {new} 
        ? {if}
        ~ {else}
        -> {inherit from}
        ; {then}
        ;= {then it}{store}
        ;-- {then it} {decrement}
        ;++ {then it} {increment}
        etc.
        {not} operator `this can be inserted within function name (that return bool value only) 
        `e.g. x [is {not} even] 
        `this will invert the boolean outcome of the function
        `comment operator
    `overloadble operator (operator that can be rewritten as function)
        + plus operator (unary and binary)
        - minus operator (unary and binary)
        * multiply operator
        / divide operator
        == {is}



`non atomic operators/functions defined in the Pineapple Standard Library (current comitee: 1. Wong Jia Hau) 
`since there are 2 names for a function (the terse one or the verbose one), one can choose to use either one
`so the function name will be the documentation for the operator itself
`the IDE should have spectacles mode to allow user to read in terse/verbose mode
`these operator can be overloaded as long as the parameters defined is not the same as the orginal one
    -   [cons]              'pine' - 'apple' == 'pineapple'
    @   [to string]         x = 4, x@ `will result in '4'
    ^   [power]             x ^ y 
    ||  [or]                x || y
    &&  [and]               x && y
    !   [not]               !x 
    |   [bitwise or]        x | y
    &   [bitwise and]       x & y
    ~   [bitwise not]       ~x
    <<  [shift left by]     x << y
    >>  [shift right by]    x >> y
    !=  [is not equal to]   x != y
    
    
`defining a function that have operator and function name
num ! : num
num [factorial] : num 
    x = 1
    [for] i [in] {1 ... param1}
        x *= i
    :x

`data type defined in the PSL
    num `which is all real numbers , e.g. 0, 12.5, -12.4 
    int -> num      `int is a num 
    unsigned -> int `unsigned is an int
    string 
    char `symbols and letters, need not to be quoted in single quote
    bool `yes, no 
    any `superset of every data type
    nil `subset of every data type
    statement `e.g. function call, variable declaration
    flow `flow of the program, not really a data type
    void 
    type `the data type of a variable
 
 
    
`declaring a variable
x : int 
a number : int
a character : char
a string : string

`literals
123 `int
$c `char'
'hello' `string
yes `bool
no `bool
nil `nil

`initializing a variable, data type is not needed to be clarified
`the '=' sign indicate that the variable is mutable
`the ':' sign indicate that the variable is immutable
x :int = 5 `the int is redundant 
c = $a 
y = 'c'
name = "hello"
is handsome = yes
pi : 3.1415 
pi = 6 `this will cause compilation error, because pi is immutable

`aliasing
x = 5
y :: x 
y = 6 
`now x will have the value of 6

`dynamic binding
x : any 
x = 6 
x = $c `this will not cause error 

`static binding
x : int
x = 7
x = 8.9 `this will cause error, because x is expecting int value
x = $c `this will also cause error


`this function takes a -num- value as prefix parameter, and will return a -num- value
`remember colon( : ) means return
num [square] : num : param1 * param1 

`note that the parameter can be in any place, and also the function name
num [is between] num [and] num : bool
    param1 
        < param2 ?: no
        > param3 ?: no
    : yes
    
`declaring operator function
int ^ int : int 
    x = 1
    [repeat] param2 [times]
        x *= param1
    : x

`this func is mutating the input, so the IDE will highlight this func to indicate that it will bring side effects
int ++ : void
    param1 += 1

square + square : square
    r = square 
    r.height = param1.height + param2.height
    r.width = param1.width + param2.width
    : r

`if statement are evaluated from top to bottom, no statement will be skipped
num <= num <= num : bool
    param2 
        < param1 ?: no
        > param3 ?: no
    : yes




square [to string] : string
    s = 
        param1.height [to string] -
        param1.width [to string]
    : s
    
`rules for defining operator
    -operator can be any symbols that are not alphanumeric
    -no spaces can contain between operator name, e.g. ==> is valid but = => is not valid
    -return, assignment, conditional operator cannot be overloaded

`calling a function
[main]
    x = 2 [square]
    2 <= x <= 3 
        [print] "x is between 2 and 3"
    

`how to implement list 
x = {int}
y = {1, 2, 3, 4, 5} 
infinite list = {1, 2, 3, ...}
finite list = {2, 4, 6, ... 100}



`accessing list element
`first element have index of 0 
`last element have index of -1
x = {$a, $b, $c, $d, $e}
x.0 `is $a
x.1 `is $b
x.-1 `is $e
x.-2 `is $d

a = 0
x.a ` which is $a

`a list does not necessary carry the same type of element
list of anything = {$a, "hello", yes, nil, 123}
list of anything.3 `is nil

`nested list 
nested = {{1,2},{3,4}}
nested.0.0 `is 1
nested.1.1 `is 3
y = {1, {2,3}, $c} `list can be uneven 
y.0 `is 1
y.1 `is {2,3}

`conditional operator
1 < 2  ? console\[print] '1 is less than 2'
#this means, if 1 is less than 2, print ...

`nested conditioning
x = 5
x
    > 0 ?   console\[print] " x is positive"
    < 0 ?   console\[print] " x is negative"
    == 0?   console\[print] "x is zero" 
    
`abstract data type
fraction
    numerator : int
    denominator : int

`constructor is actually a function
`they will be call fake constructor
int [over] int : fraction
    r = fraction
    r.numerator = param1
    r.denominator = param2
    : r 

`using the fake constructor
x : fraction = 3 [over] 4 

`using the actual constructor
mutable fraction  = fraction | numerator = 3 , denominator = 4 
immutable fraction : fraction | numerator = 4 , denominator = 6
mutable fraction += 3[over]4

point
    x:int
    y:int
    
point1 = point | x = 3 , y = 4
point1 [translate by] 1 , 2


`inheritance
point with mass -> point     `this means point with mass is inheriting from point
    mass:num

p = point with mass | x = 3, y = 4, mass = 5.6

`multiple inheritance 
dog -> animal, pet

dog [bark] : void
    [print] "wuf wuf"

`defining an interface 
car [move] : void
car [brake] : void
car [open light] : void

`inheriting from interface
`note that honda needs not to provide definition for all the functions inherited from car
`error will only be raised during compile-time if honda is trying to invoke a function that it hasn't give ant definition
honda -> car

`enumeration 
`in pineapple they are just int bounded with a name, so any int operation can work on them
`the double colon operator is the alias operator
`it means the value on the left is same as the right, and vice versa
day \\ monday::1 , tuesday::2, wednesday::3, thursday::4, friday::5, saturday::6, sunday::7

`declaring enum type variable
x : day
y = day\monday
z = day\1 `which is monday as well

num [days later is] day : bool
    system\current\date.Day + param1 == param2 ? : yes
    ~ : no

day + num : day 
    : (param1 + param2)

day [next day] : day
    : (param1 + 1) [modulo] 7
    

`multiple conditional statement
console\[print] 'enter a number'
x = [get input from] io\keyboard 
x[is parsable to int]?
    x
        [is positive] ? [print] 'x is positive'
        [is negative] ? [print] 'x is negative'
        [to string][is substring of][pi][to string] ? 'x is pi'
~[print] 'i tell you to enter a number right?'


`pattern matching
0   [factorial] : 1 
num [factorial] : num
    : param1 * (param1 - 1)[factorial]
    
`factorial can also be defined in this way 
0 ! : 1 
num ! : num
    : param1 * (param1 - 1)!

`grouping functions
math\
    num [ln] num : num `currently definitionless
    pi : 3.1415

`using grouped function
apple =  math/ 2 [ln] 3 
[print] 'enter the radius of a circle'
radius = [get input from] keyboard
area = 2 * math\pi * radius
[print] 'the area of the circle is' - area[to string with] 2 [decimal point] - 'unit' - ASCII\superscript_2[to string]

`num function 
num [to string with] num [decimal point] : string
num [to string with] num [significant figure] : string
num [to string in scientific form] : string
num [to string in base] num : string

`unit test
num [square] : num
    : param1 * param1
test.input = { 2, 3, 4 }
test.expected output = { 4, 9, 16 }
`if the actual output does not match expected output, warning will be generated by compiler



    


`counted loop
[repeat for] 5 [times]
    [print] "Hello world!"

`for each loop
x = "hello"
[for] c [in] x
    [print] c

`infinite loop
[repeat forever]
        

num [is positive] : bool
    param1 > 0 ? :yes
    :no


`if else
[print] "enter a number"  
x = [get input]
x[is parsable to int]? 
	x > 0 ? [print] "x is greater than 0"
	x < 0 ? [print] "x is lesser than 0"
~[print] "walao a i tell you a number leh"

===============================================================================
`implementation of linked list in Pinapple Language
`to demonstrate how generic programming works 
node
    data : any
    next node : node
    Type : type

node [get data] : any 
    : list.data
    
node [get next] : node 
    : list.next node 
    
node [set next] node : void 
    param1.type != param2.type ? : error
    param1.next node = param2

linked list
    head : node
    Type : type

linked list [insert] any : void
    param2.type != param1.head.type ? : error 
    new node = node | data = param2 , next node = nil, Type = param2.type
    new node [set next] param1.head
    param1.head = new node
    
linked list [size] : int
    current = param1.head
    count = 0
    [while] current != nil 
        count++
        current = current[get next]
    :count
    
linked list [search] any : any
    current = param1.head
    [repeat forever]
        current[get data] ==
            param2 ?: current
            nil ?: nil
        current = current[get next]

linked list [is empty] : bool
    : param1.head == nil

[linked list of] type : linked list
    x = linked list | head = nil, Type = param1
    : x

[main]
    `note that the type dont have to be mentioned actually
    `i type that so that the IDE can scope which function will return linked list
    x : linked list = [linked list of] int
    x[insert]5 
    x[insert]6

`==========================================================================================
`example of classes
clock 
    hour : int
    minute : int
    second : int

clock [set time, hour] num [minute] num [second] num : void
    param1.hour = param2
    param1.minute = param3
    param1.second = param4
    :
    
clock @ : string
clock [to string] : string
    : param1.hour@ - ':' - param1.minute@ - ':' - param1.second@ 

[main]
    rolex : clock
    rolex [set time, hour] 5 [minute] 5 [second] 5 
    console\[print] rolex@
    
    
 
        
    





    


#basically anything is possible 


    


#sample programs
#hello world
[main] 
    [print] "Hello world"

#max function
[max] num num : num 
    param1 > param2 : param1
    : param2

#--
[main]
    a = 100
    b = 50
    result = [max] a b
    [print] "max value is " result[to string]

`token stream
'token stream'
    counter = 0
    input  string

'token stream' [next] : string : param1.input.(counter + 1)
'token stream' [previous] : string : param.input.(counter-1)
'token stream' [go to next] : void : param1.counter++


class TokenStream{
    int counter;
    string input;
    
    public:
        void Next() const { } 
    }




`to string functions
int [to string] : string 
char [to string] : string
{int} [to string] : string

bool [and] bool : bool
    param1 == yes && param2 == yes ? : yes
    :no
    
[pi] : num : 3.14

y = string
x = "ny"



#BNF form
<func_def_stmt> -> {<data_type>} [func_id] <pfd>  : <data_type> #pfd means partial function definition
<func_body>

<func_body> -> {<stmt>}

<stmt> 
-> <if_stmt>
-> <assign_stmt>

<if_stmt>
-> <expr> ? <stmt>

<pfd> 
    -> <data_type> 
    -> <data_type> [func_id] 
    -> {<pfd>}
    

    
<func_def_stmt>
=> <prefix_pfd> [func_id] <postfix_pfd> : <data_tyoe>
=> nothing [func_id] <postfix_pfd> 
=> nothing [max] <postfix_pfd>
=> nothing [max] <postfix_pfd> <postfix_pfd>
=> nothing [max] <data_type> <data_type>
=> nothing [max] num num



<func_def_stmt>
=><prefix_pfd> [func_id] <postfix_pfd> : <data_type>
=><prefix_pfd><prefix_pfd>[func_id]<postfix_pfd> : <data_type>
=><data_type> <prefix_pfd>          [func_id]<postfix_pfd> : <data_Type>
=><data_type> [func_id] <data_type> [func_id]  <data_type> : <data_type>

1 [is between] 2 [and] 3 [and] yes
1 is between 2 and 3 and yes
x is between y and z and yes

num [is between] num [and] num : num
param1 > param3 ? : no
param1 < param2 ? : no
: yes
    



