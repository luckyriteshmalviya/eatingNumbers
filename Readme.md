# \* A number can eat the number to the right of it if it's smaller than itself. After eating that number, it becomes the sum of itself and that number. Your job is to return the final array after the leftmost element has finished "eating".

    Constraints
    • Each array has at least 2 elements.
    • Each element is an integer.

    Input Format
     The first line contains an integern,the number of
    elements in input array The next line contains space
    separated integers,i.e.,Array elements.

    Output Format
     Your function should return an array of integers.


    Example no.1 :-
     [5,3,7]
    Process:- [5,3,7]=>[8,7]=>[15]
    5 eats 3 to become 8
    8 eats 7 to become 15
    Output :- [15]

    Example no.2 :-
    Inpout :-
    3
    [5 1 9]
    Output :-[6 9]
    */

/\*\*
## Algorithm  
- Step 001 - Check wheather the input is valid or not by using if-else condition.
- Step 1.1 - If not just return the message - "Please Enter Valid Input."
- Step 002 - Create a variable "arrayLength" for optimization purpose.
- Step 003 - Start Iteration on the inputArr by using for loop.
- Step 004 - Apply a condition if value of leftmost index (0) is greater than value of next index (1).
- Step 4.1 - If yes then Create a new variable sum which i sthe sum of both value.
- Step 4.2 - Now replace this value with the both value of inputArr.
- Step 4.3 - Now subtract 2 from current index so it will start iterating again from current value.
- Step 4.4 - Apply continue so the iteration keeps gong on untill the last possible execution.
- Step 005 - Return the inputArr.
  \*/
  
  ## Approach no.1 :-  
function eatingNumbers(inputArr) {  
// Gaurd Block Approach  
// if (!inputArr || !Array.isArray(inputArr) || inputArr.length <= 1) {  
// return "Please Return Valid Input.";  
// }  
if (inputArr && Array.isArray(inputArr) && inputArr.length > 1) {  
let arrayLength = inputArr.length;  
for (let i = 0; i < arrayLength; i++) {   
if (inputArr[0] > inputArr[1]) {  
let sum = inputArr[i] + inputArr[i + 1];   
inputArr.splice(i, 2, sum);  
i = i - 1;  
continue;  
}  
}  
return inputArr;  
}  
return "Please Enter Valid Input.";  
}  
let arr = [2, 1, 7];  
console.log(eatingNumbers(arr));  
  
