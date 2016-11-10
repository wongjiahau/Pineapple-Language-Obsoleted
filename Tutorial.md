# The Pineapple Language 
## Tutorial 
*This tutorial will be done by showing pineapple in terse and verbose mode.*

|   Statement  |Terse|Verbose|  
|:----:|:---:|:--:|  
|Assignment|x = 5|x {as} 5|  
|If | x == 5 ? | {if} x {equals} 5|  
|If-else| x==5 ? [eat apple] <div>~ [eat banana] |{if} x {equals} 5 {then} [eat apple] <div> {else} [eat banana]  
|Return| : x |{return} x  
|Inheritance| x -> y | x {is a} y  

*Now lets look at the primitive data type* 

Type|Representation| 
|:----:|:---: 
int| -1 ，23 ， 99  
num| -1 , 23 , 0.99 , .88  
char| $a , $b , $c  
string| 'pen' , 'pineapple' , 'a'  
bool| yes , no  
any| *Any type can be assigned to this data type.*  
nil| *Can be assigned to any data type.*  
---  
### Function definition  
Let's look at it's BNF form first (you may skip this part if you don't know BNF)

```
func_def_stmt -> 
{data_type}  func_id  pfd  ':' data_type 
'\t' func_body
pfd //pfd means partial function definition
    -> data_type 
    -> data_type func_id 
    -> {pfd}
func_body -> 
	{<stmt>}
func_id 
	-> '[' id ']' 
    -> symbol
```
Sample code
```
`definition
num [square] : num
	: param1 * param1

`function calling
x = 5 [square]
```
```
`definition
bool [and] bool : bool
	no ==
    	param1 ? : no
        param2 ? : no
    : yes

`function calling
is happy = yes
is crazy = yes
is crazy [and] is happy ? [print] 'is hobo'
```
```
`definition
[max of] (num) : num
	max = param1.0
    {for} a {in} param1
    	a > max ? max = a
    : max

`function calling
x = (1,2,3,4,5) 
y = [max of] x
```
```

```
*to be continued...*








