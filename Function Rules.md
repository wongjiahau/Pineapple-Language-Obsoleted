
# Function Rules  
---  
## [1] There are only 2 kind of functions, the **void** function and **non-void** function. 
   1) **VOID** function : MUST NOT return value, but it will cause ***side effects***.  
   2) **NON-VOID** function : MUST return at least a value, but it cannot cause side effects (*which is to change the state of the passed in parameter(s))*
   * So it is invalid to define a function that returns a value AND cause side effects (this is to inline with the ***Single Responsiblity Principle [SRP]*** )
 
---
Example :  
```  
`this function will cause side effects
any [swap] any : void
	temp = param1
    param1 = param2
    param2 = temp
    :

`this function will not cause side effects
num [is odd] : bool
	param1[mod]2 == 1 ? : yes
    ~ : no

`this function is invalid
[do random stuff to] num : bool
	param1 = param1 + 1
    : param1 + 2
```
---
## [2] Function name can be in any pattern as long as every function ID is followed by a parameter and vice versa.  
	 
   * This is to inline with the ***Meaningful Name Principle***
    
   
---
Example:  
```
`All the function name definitions below is valid
`--------------------------------------------------------------
[say hello] : void	

num [factorial] : num 	

[halve] num : num

bool [and] bool : bool 

[substring of] string [from index] num [to] num : string

[sort] {num} : void
`--------------------------------------------------------------
`--------------------------------------------------------------
`Below are invalid function name definitions
`--------------------------------------------------------------
[say][good morning] : void 

[max of] num num : num

num [add][by] num char : void

```
---
## [3] Precedence 
Precedence|Type|Example
:---:|:---:|:---:
Highest|Prefix Unary|`[print] string : void`
2nd Highest|Postfix Unary |`num [square] : num`
3rd ...|Binary| `bool [and] bool : bool`
4th ... |Ternary|`[substring of] string [from index] num [to] num : string`
... |...|...
*n*-th|*n*-th-nary|...
*Of course the same goes for Symbolic Functions. (Which uses symbol as name).*  
Example : 
```
a = 'pineapple' 
b = 2
c = [substring of] a [from index] b [square][plus] 1 [to] 6
```
The evaluation order will be :  
   1) `b [square]`  ( let's say it yields x , and the following will also yield x)  
   2) `x [plus] 1`  
   3) `[substring of] a [from index] x [to] 6 `  

---   
## [4] Associativity 
Easy, you just have to remember the **First Come First Serve** rule.
Of course, this rule comes in when comparing to functions that have the same precedence.
 
 Now look at this statement : `a + b * c`  
 Is it `b * c` will be done first ? The answer is NO.  
 `a+b` will be done first.  
 *So precedence is only measure by their type (e.g. unary, binary etc), so no need to memorize the precedence table : )*
 
 ---   
 
 ## [5] Coming soon ... 
