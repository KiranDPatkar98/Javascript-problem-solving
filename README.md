# JavaScript Questions

## 1. Count the number of vowels in the string

```javascript
const countVowels = (value) => {
    const lowerCase = value.toLowerCase();
    let count = 0;
    const vowels = ['a', 'e', 'i', 'o', 'u'];
    for (let i = 0; i < lowerCase.length; i += 1) {
        if (vowels.includes(lowerCase[i])) {
            count += 1;
        }
    }
    return count;
}

console.log(countVowels('KDpio0oaaa'));

```


## 2.  Count the number of unique vowel in the string
```javascript
const countVowels=(value)=>{
    const lowerCase=value.toLowerCase()
    const vowels=['a','e','i', 'o','u']
    const presentVowels=[]
    let count=0;
    for (let i=0;i<lowerCase.length;i+=1){
        if(vowels.includes(lowerCase[i])&& !presentVowels.includes(lowerCase[i])){
            count+=1;
            presentVowels.push(lowerCase[i])
        }
    }
    return count
    
}
console.log(countVowels('KiranaaaWery'))

```
## 3. Write a JavaScript function named getDenominations that takes two parameters - amount (target amount) and denominations (an array of available denominations in descending order). The function should return an object representing the count of each denomination needed to represent the given amount. Provide an example usage with denominations [2000, 500, 100] and an amount of 6700.

```javascript
const getDenominations=(amount,denominations)=>{
    const sortedDenomination=denominations.sort((a,b)=>b-a)
    const res={}
    for(let i=0; i<sortedDenomination.length; i+=1){
        const count=Math.floor(amount/sortedDenomination[i])
        if(count>0){
        res[sortedDenomination[i]]=count;
        amount=amount%sortedDenomination[i]
        } else{
        res[sortedDenomination[i]]=0
        }
    }
    return res
}

console.log(getDenominations(6700,[2000,500,300,100]))
```

## 4. // console the object values so the function should work dynamic for any object's
```javascript
const objectValue={
    'employees':{
        'employeename':'Nanda',
        'employeeId':"123",
        'employeeAddress':{
            'location':'Bangalore'
        }
    },
}
// output should come like this
    // 'employeename':'Nanda',
    // 'employeeId':'123',
    // 'location':'Bangalore',
Answer:
const keyValuePairs=(obj)=>{
for (const key in obj){
    if(typeof obj[key] ==='object'){
        keyValuePairs(obj[key])
    }else
    {
        console.log(`${key} : ${obj[key]}`)
    }
}
}
console.log(keyValuePairs(objectValue))
```

## 5. Javascript program to check Prime number
```javascript
const isPrime=(number)=>{
    if (number < 2) {
        return false;
    }
    for(let i=2;i<=Math.sqrt(number);i+=1){
        if(number % i===0){
            return false
        }
        return true
    }
}
console.log(isPrime(11))
```

## 6. JavaScript Program to Print All Prime Numbers in an Interval
```javascript
const checkPrime=(number)=>{
    for(const i=2; i<=Math.sqrt(number); i+=1){
       if(number % i===0){
           return false
       } else{
           return true
       }
    }
}

const printPrimeNumbers=(range1, range2)=>{
    for(let i=range1; i <=range2; i+=1){
       if(checkPrime(i)){
           console.log(i)
       }
    }
}
console.log(printPrimeNumbers(100, 150))
```

## 7 Move all the zeros at the end of list
```javascript
const moveZeros=(list)=>{
    const zeros=[]
    const nonZeros=[]
    for (let i=0; i<list.length; i+=1){
        if(list[i]!==0){
            zeros.push(list[i])
        }else{
            nonZeros.push(list[i])
        }
    }
    return zeros.concat(nonZeros)
}
console.log(moveZeros([1,0,2,3,0,0,2,5]))
```

