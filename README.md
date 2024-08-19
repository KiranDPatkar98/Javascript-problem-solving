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
    }
return true
}
console.log(isPrime(11))
```

## 6. JavaScript Program to Print All Prime Numbers in an Interval
```javascript
const checkPrime=(number)=>{
    for(const i=2; i<=Math.sqrt(number); i+=1){
       if(number % i===0){
           return false
       } 
    }
return true
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

## 8 JavaScript Program to Find the Factorial of a Number

```javascript

const factorial=(number)=>{
    let fact=1;
    for (let i=number;i>=1;i--){
        fact=fact*i
    }
    return fact
}
console.log(factorial(0))
```

## 9 JavaScript Program to print the Fibonacci sequence

```javascript

const fibonacci=(range)=>{
    const fib=[0,1]
    for(let i=2; i<range; i+=1){
        fib.push(fib[fib.length-1]+fib[fib.length-2])
    }
    return fib
}
console.log(fibonacci(20))
```

## 10 You are given a string and you need to rotate it based on the specified position and direction.

```javascript

const rotateString=(string, position,direction)=>{
    const sliceValue =direction==='left'? 1 :-1
    // if(sliceValue===1){
    // return string.slice(position)+string.slice(0,position)
    // }
    // return string.slice(-position)+ string.slice(0, -position)
    return string.slice(position*sliceValue)+ string.slice(0, position*sliceValue)
    
}


console.log(rotateString('python',2 ,'left'))  //thonpy
console.log(rotateString('python',2 ,'right')) //onpyth

```

## 11 Find the Index of the First Occurrence in a String.
```javascript
        ### Without using methods
        
        const findIndex=(sentence, search)=>{
            for(let i=0;i<=sentence.length-1;i+=1){
               let found=true;
               for(let j=0; j<=search.length-1; j+=1){
                   if(sentence[i+j] !== search[j]){
                       found=false
                       break
                   } 
               }
               if(found){
                   return i
               }
           }
           return -1
        }
        
       
        ### Using method

        
        const findIndex=(sentence, search)=>{
           
           return sentence.indexOf(search)
        }
        
        console.log(findIndex('kiran is bad', 'bad'))
```

## 12  Find the indexes of target value which is provided using o(n)
```javascript
const arr=[4,7,8,1,3,2,5,12]

const findIndices=(arr, target)=>{
    const obj={}
    for(let i=0;i<=arr.length-1; i+=1){
       if(arr[i] in obj){
           return [obj[arr[i]],i]
       }else{
               obj[target-arr[i]]=i 
       }
   
    }
    return obj
}

console.log(findIndices(arr, 13))  // [ 2, 6 ]
```
## 13 Find the count of consecutive number 
## input=[1,1,1,1,2,2,3,3,3,4,4,4,1,1]
## output=[4,2,3,3,2]

```javascript
const findConsecutiveCount=(array)=>{
    const newArr=[]
    let temp;
    for(let i=0; i<=array.length-1;i+=1){
       if(temp===array[i]){
           newArr[newArr.length-1]=newArr.at(-1)+1
       }else{
           temp=array[i]
           newArr.push(1)
       }
    }
    return newArr
}
console.log(findConsecutiveCount([1,1,1,1,2,2,3,3,3,4,4,4,1,1]))
```
## 14 Two sum [Problem Statement](https://leetcode.com/problems/two-sum/)

```javascript

const twoSum = function(nums, target) {
    const data={}
    for (let i=0; i<=nums.length-1; i+=1){
        if(nums[i] in data){
            return [data[nums[i]], i]
        }
    data[target-nums[i]]=i
    }
};

```
## 15 Best time to buy and sell stock [Problem statement](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

```javascript
var maxProfit = function(prices) {
    let buying_price=prices[0]
    let maxProfit=0
    for(let i=1; i<=prices.length-1;i+=1){
     buying_price=Math.min(prices[i],buying_price)
     maxProfit=Math.max(maxProfit,prices[i]-buying_price)
    }
    return maxProfit
    
};

```

## 16 Maximum sum of the sub array [Problem Statement](https://leetcode.com/problems/maximum-subarray/description/)

```javascript

var maxSubArray = function(nums) {
    let maxSum=nums[0];
    let currentSum=nums[0]
    for (let i=1;i<=nums.length-1; i+=1){
       currentSum=Math.max(nums[i], currentSum+nums[i])
       if(currentSum>maxSum){
        maxSum=currentSum
       }

    }
    return maxSum
};

```

## 17 Find the single number [Problem Statement](https://leetcode.com/problems/single-number/description/)

```javascript

var singleNumber = function(nums) {
    const obj={}
    for(let i=0; i<=nums.length-1;i+=1){
     if(nums[i] in obj){
        delete obj[nums[i]]
     }else {
        obj[nums[i]]=nums[i]
     }
    }
    for (item in obj) return obj[item]
};

```
