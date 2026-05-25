// makeGreatString
let str = "haAarish";
// Aa are 2 adjacent characters , we need to remove also next aa is small , it should not remove

// use stack method to remove adjacent chars. 
// Note : stack means LIFO last In First Out.
// we can use for-of method with stack array
// Remember : push and pop in arrays. push =insert at last index.
// pop = Remove last index
// 1. Initially stack will be empty and length is 0, insert 1st char
// 2. next check the char with stack's last data, if both are same and case insensitive then pop out from the stack
// 3. then in the final array, use join to convert to string.

function makeGreatString(data) {
    let stack =[];
    
    for (let char of data) {
        if(stack.length >0 &&
            stack[stack.length-1] !== char &&
            stack[stack.length-1].toLowerCase() === char.toLowerCase()
            ) {
            stack.pop();
        }
        else
        {
            stack.push(char);
        }
        
        }
        console.log("great string : "+ stack.join(""))
    }


makeGreatString(str);


-------xxxx-----xxxxxxx---------xxxxx---

