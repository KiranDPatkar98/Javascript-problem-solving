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


##2  Count the number of unique vowel in the string
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
