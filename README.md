# The Pineapple Language 
#### By: Wong Jia Hau
### 4 pillars of the design: (**T.R.O.L.**)

>1. **Typability** 
>2. **Readability** 
>3. **Orderity**  (*Anti-dirty code*)
>4. **Learnability** 


---
### Sample code 
*This will be done by comparing C++ with Pineapple*
>**About Readability**
>> C++
>>
>> ```java
>> bool is_between (int x, int y, int z){
>> 	return x >= y && x <= z;
>> 	}
>>int main(){
>>	int pen = 3, pineapple = 4, apple =5;
>>	if(is_between(pen, pineapple, apple)) cout << "ppap" ;
>>} //Is "ppap" going to be printed out?
>>```
>> Pineapple
>>```
>>int [between] int [and] int : bool
>>    : param1 >= param2 [and] param1 <= param3 
>>
>>[main]
>>    pen = 3
>>	  pineapple = 4
>>    apple = 5
>>	  pen [is between] pineapple [and] apple ? [print] "ppap" 
>>    `Is "hey" going to be printed out?
>>```
>> Pineapple (done by experienced Pineappler)
>>```
>>int <= int <= int : bool
>>    : param1 <= param2 [and] param2 <= param3
>>    
>>[main]
>>    pen = 3
>>	  pineapple = 4
>>    apple = 5
>>	  pineapple <= pen <= apple ? [print] "ppap" 
>>    `Is "hey" going to be printed out?
>>```
---
>**About Typability**
>> C++
>>
>> ```java
>>int main(){
>>    int pen = 99
>>    if(pen < 10) cout << "p";
>>    else if(pen == 100) cout << "pp";
>>    else if(pen > 1000) cout << "ppa";
>>    else cout << "ppap"; 
>>} 
>>```
>> Pineapple
>>```
>>[main]
>>    pen = 99
>>    pen
>>        < 10 ? [print] "p"
>>        == 100 ? [print] "pp"
>>        > 1000? [print] "ppa"
>>    ~ [print] "ppap" 
>>```
---
>**About Learnability**  
>*In Pineapple you can switch between terse / verbose mode*
>> Pineapple
>>```
>>[main] `terse mode
>>    pen {as} 99
>>    {if} pen
>>        {less than} 10 {then} [print] "p"
>>        {equals} 100 {then} [print] "pp"
>>        {more than} 1000 {then} [print] "ppa"
>>    {else} [print] "ppap" 
>>```
---
>**About Orderity**  
>*Since operator overloading and logical function name can be build easily, the pineapple code will be as ordered as the thorns of pineapple.*

---
###### Please contact me if you are interested, 011-16372171.








