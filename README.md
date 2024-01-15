```1 ) // count the number of vowels in the string

const countVowels=(value)=\>{ const lowerCase=value.toLowerCase() let
count=0; const vowels=\[\'a\',\'e\',\'i\', \'o\',\'u\'\] for (let
i=0;i\<lowerCase.length;i+=1){ if(vowels.includes(lowerCase\[i\])){
count+=1; } } return count

} console.log(countVowels(\'KDpio0oaaa\'))

2\) Count the number of unique vowel in the string

const countVowels=(value)=\>{ const lowerCase=value.toLowerCase() const
vowels=\[\'a\',\'e\',\'i\', \'o\',\'u\'\] const presentVowels=\[\] let
count=0; for (let i=0;i\<lowerCase.length;i+=1){
if(vowels.includes(lowerCase\[i\])&&
!presentVowels.includes(lowerCase\[i\])){ count+=1;
presentVowels.push(lowerCase\[i\]) } } return count

} console.log(countVowels(\'KiranaaaWery\'))

3)Write a JavaScript function named getDenominations that takes two
parameters - amount (target amount) and denominations (an array of
available denominations in descending order). The function should return
an object representing the count of each denomination needed to
represent the given amount. Provide an example usage with denominations
\[2000, 500, 100\] and an amount of 6700.

const getDenominations=(amount,denominations)=\>{ const
sortedDenomination=denominations.sort((a,b)=\>b-a) const res={} for(let
i=0; i\<sortedDenomination.length; i+=1){ const
count=Math.floor(amount/sortedDenomination\[i\]) if(count\>0){
res\[sortedDenomination\[i\]\]=count;
amount=amount%sortedDenomination\[i\] } else{
res\[sortedDenomination\[i\]\]=0 } } return res }

console.log(getDenominations(6700,\[2000,500,300,100\]))

4\) // console the object values so the function should work dynamic for
any object\'s const objectValue={ \'employees\':{
\'employeename\':\'Nanda\', \'employeeId\':\"123\",
\'employeeAddress\':{ \'location\':\'Bangalore\' } }, } // output should
come like this // \'employeename\':\'Nanda\', // \'employeeId\':\'123\',
// \'location\':\'Bangalore\',

const keyValuePairs=(obj)=\>{ for (const key in obj){ if(typeof
obj\[key\] ===\'object\'){ keyValuePairs(obj\[key\]) }else {
console.log(\`\${key} : \${obj\[key\]}\`) } } }
console.log(keyValuePairs(objectValue))
```
