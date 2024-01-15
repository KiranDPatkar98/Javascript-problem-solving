JavaScript Interview Questions & Answers

<!-- 1) Count the number of vowels in the string -->

const countVowels = (value) => {
    const lowerCase = value.toLowerCase()
    let count = 0;
    const vowels = ['a', 'e', 'i', 'o', 'u']
    for (let i = 0; i < lowerCase.length; i += 1) {
        if (vowels.includes(lowerCase[i])) {
            count += 1;
        }
    }
    return count
}

console.log(countVowels('KDpio0oaaa'))

<!-- 2) Count the number of unique vowels in the string -->

const countVowels = (value) => {
    const lowerCase = value.toLowerCase()
    const vowels = ['a', 'e', 'i', 'o', 'u']
    const presentVowels = []
    let count = 0;
    for (let i = 0; i < lowerCase.length; i += 1) {
        if (vowels.includes(lowerCase[i]) && !presentVowels.includes(lowerCase[i])) {
            count += 1;
            presentVowels.push(lowerCase[i])
        }
    }
    return count
}

console.log(countVowels('KiranaaaWery'))

<!-- 3) Calculate denominations needed for a given amount -->

const getDenominations = (amount, denominations) => {
    const sortedDenomination = denominations.sort((a, b) => b - a)
    const res = {}
    for (let i = 0; i < sortedDenomination.length; i += 1) {
        const count = Math.floor(amount / sortedDenomination[i])
        if (count > 0) {
            res[sortedDenomination[i]] = count;
            amount = amount % sortedDenomination[i]
        } else {
            res[sortedDenomination[i]] = 0
        }
    }
    return res
}

console.log(getDenominations(6700, [2000, 500, 300, 100]))

<!-- 4) Log object values dynamically -->

const objectValue = {
    'employees': {
        'employeename': 'Nanda',
        'employeeId': "123",
        'employeeAddress': {
            'location': 'Bangalore'
        }
    },
}

const keyValuePairs = (obj) => {
    for (const key in obj) {
        if (typeof obj[key] === 'object') {
            keyValuePairs(obj[key])
        } else {
            console.log(`${key} : ${obj[key]}`)
        }
    }
}

console.log(keyValuePairs(objectValue))

<!-- 5) Javascript program to check Prime number -->

const isPrime = (number) => {
    if (number < 2) {
        return false;
    }
    for (let i = 2; i <= Math.sqrt(number); i += 1) {
        if (number % i === 0) {
            return false
        }
        return true
    }
}

console.log(isPrime(11))

