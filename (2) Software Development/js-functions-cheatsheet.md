# JavaScript Functions Cheatsheet

## 1. 📜 String Functions
```js
1. str.charAt(index)         // Get character at index
2. str.concat(otherStr)      // Concatenate strings
3. str.includes(subStr)      // Check if string contains substring
4. str.indexOf(subStr)       // Index of first match
5. str.lastIndexOf(subStr)   // Index of last match
6. str.replace(old, new)     // Replace substring
7. str.slice(start, end)     // Extract part of the string
8. str.split(delimiter)      // Convert string to array
9. str.substring(start, end) // Similar to slice, no negatives
10. str.toLowerCase()        // Convert to lowercase
11. str.toUpperCase()        // Convert to uppercase
12. str.trim()               // Remove whitespace from both ends
```

## 2. 🔢 Number Functions
```js
1. parseInt("42")             // Convert to integer
2. parseFloat("3.14")         // Convert to float
3. num.toFixed(2)             // Format with 2 decimal places
4. isNaN(value)               // Check if value is NaN
5. Math.round(num)            // Round to nearest integer
6. Math.floor(num)            // Round down
7. Math.ceil(num)             // Round up
8. Math.random()              // Random number [0, 1)
9. Math.max(...nums)          // Max value
10. Math.min(...nums)         // Min value
```

## 3. 📚 Array Functions
```js
1. arr.push(item)             // Add item to end
2. arr.pop()                  // Remove last item
3. arr.shift()                // Remove first item
4. arr.unshift(item)          // Add item to start
5. arr.slice(start, end)      // Return portion of array
6. arr.splice(start, count, items) // Remove/replace/add
7. arr.concat(otherArr)       // Merge arrays
8. arr.join(separator)        // Join elements into string
9. arr.indexOf(item)          // First index of item
10. arr.includes(item)        // Check if item exists
11. arr.forEach(fn)           // Run function on each item
12. arr.map(fn)               // Transform array
13. arr.filter(fn)            // Filter by condition
14. arr.reduce(fn, initial)   // Accumulate to single value
15. arr.find(fn)              // Find first match
16. arr.some(fn)              // Any item passes condition
17. arr.every(fn)             // All items pass condition
```

## 4. 🧱 Object Functions
```js
1. Object.keys(obj)           // Get keys array
2. Object.values(obj)         // Get values array
3. Object.entries(obj)        // Get [key, value] pairs
4. Object.assign(target, src) // Merge objects
5. obj.hasOwnProperty(key)    // Check if key exists
6. delete obj.key             // Remove property
7. JSON.stringify(obj)        // Convert to JSON string
8. JSON.parse(json)           // Convert JSON string to object
```

## 5. 🛠️ Utility Functions
```js
1. setTimeout(fn, ms)         // Delay function
2. setInterval(fn, ms)        // Repeated function
3. clearTimeout(id)           // Cancel timeout
4. clearInterval(id)          // Cancel interval
5. typeof value               // Get data type
6. Array.isArray(value)       // Check if value is array
7. isFinite(value)            // Check if value is finite number
```
