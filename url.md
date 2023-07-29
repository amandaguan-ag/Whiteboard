<!-- URLs cannot have spaces. Instead, all spaces in a string are replaced with %20. Write an algorithm that replaces all spaces in a string with %20.

You may not use the replace() method or regular expressions to solve this problem. Solve the problem with and without recursion.

Example
Input: "Jasmine Ann Jones"
Output: "Jasmine%20Ann%20Jones" -->

Clarifying question
1) Is this language JS acceptable?
2) Can I always expect a string as input? (Is it always a string, will it always contain spaces...)
3) What should the output be if the input string is empty?

Read through the prompt, explain my understanding.

Pseudo-coding/Behaviors
1) Given a string, we need to replace all spaces with "%20".
2) We should not use the `replace()` method or regular expressions to solve this problem.
3) We'll use an iterative approach to achieve this.
4) We'll create an empty result string and iterate through each character in the input string.
5) If the character is a space, we'll append "%20" to the result; otherwise, we'll append the character itself.
6) Finally, we'll return the modified result string.

// Iterative solution

function replaceSpacesIterative(str) {
    let result = "";

    for (let i = 0; i < str.length; i++) {
        if (str[i] === " ") {
            result += "%20";
        } else {
            result += str[i];
        }
    }

    return result;
}

// Example - Iterative solution
const input = "Jasmine Ann Jones";
const outputIterative = replaceSpacesIterative(input);
console.log(outputIterative); // Output: "Jasmine%20Ann%20Jones"

// Pseudo-coding/Behaviors for the recursive solution
// 1) Given a string, we need to replace all spaces with "%20".
// 2) We should not use the `replace()` method or regular expressions to solve this problem.
// 3) We'll use a recursive approach to achieve this.
// 4) The base case will be when the string is empty; in that case, we'll return an empty string.
// 5) Otherwise, we'll check the first character of the string:
//     - If it is a space, we'll return "%20" concatenated with the result of the recursive call on the remaining string (excluding the first character).
//     - If it is not a space, we'll return the first character concatenated with the result of the recursive call on the remaining string (excluding the first character).

// Recursive solution

function replaceSpacesRecursive(str) {
    if (str.length === 0) {
        return "";
    }

    if (str[0] === " ") {
        return "%20" + replaceSpacesRecursive(str.slice(1));
    } else {
        return str[0] + replaceSpacesRecursive(str.slice(1));
    }
}

// Example - Recursive solution
const outputRecursive = replaceSpacesRecursive(input);
console.log(outputRecursive); // Output: "Jasmine%20Ann%20Jones"
