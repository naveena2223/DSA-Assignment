# DSA-Assignment

console.clear()

// Question-1
function findPairs(arr, target) {
    let result = [];
    let map = {};
    for (let i = 0; i < arr.length; i++) {
        let diff = target - arr[i];
        if (map[diff] !== undefined) {
            result.push([arr[i], diff]);
        } else {
            map[arr[i]] = true;
        }
    }
    return result;
}

let arr = [1, 2, 3, 4, 5, 6, 7];
let target = 7;
let pairs = findPairs(arr, target);
console.log(pairs);


// Question-2
let arr2=[2,1,8,7,3,8,4,5]

for(var i=0; i<arr2.length/2 ; i++){

    let x=arr2.shift()
    let y=arr2.push(x)

}
console.log(arr2)

// Question-3
let str1="Hello"
let str2="olleH"
str1=str1.toLocaleLowerCase().split("").sort().join("")
str2=str2.toLocaleLowerCase().split("").sort().join("")

if(str1.length !== str2.length){
    console.log("Given two strings are not a rotation")
}else{

        if(str1===str2){

    console.log("Given two strings are  a rotation")
        
}else if(str1 !== str2 ){
    console.log("Given two strings are not a rotation")
}
}

// Question-4
let str3="naveena"

let obj1={}
let count=0

for(let i=0;i<str3.length;i++){
    if(obj1[str3[i]]){
       obj1[str3[i]] = obj1[str3[i]]+1

    }else {
        obj1[str3[i]]=count+1
    }
}

for(var i=0;i<str3.length;i++){
    if(obj1[str3[i]]===1){
        console.log(str3[i])
        break;
    }
}

// Question-5
function towerOfHanoi(n, source, auxiliary, target) {
    if (n === 1) {
        console.log(`Move disk 1 from ${source} to ${target}`);
        return;
    }

    towerOfHanoi(n - 1, source, target, auxiliary);
    console.log(`Move disk ${n} from ${source} to ${target}`);
    towerOfHanoi(n - 1, auxiliary, source, target);
}

towerOfHanoi(3, 'A', 'B', 'C');

// Question-6
function postfixToPrefix(postfix) {
    let stack = [];
    for (let i = 0; i < postfix.length; i++) {
        let token = postfix[i];
        if (isOperator(token)) {
            let operand2 = stack.pop();
            let operand1 = stack.pop();
            let result = token + operand1 + operand2;
            stack.push(result);
        } else {
            stack.push(token);
        }
    }
    return stack.pop();
}

function isOperator(token) {
    return token === '+' || token === '-' || token === '*' || token === '/';
}

let postfix = '23+';
let prefix = postfixToPrefix(postfix);
console.log(prefix);

// Question-7
const input1 = "*+ad-cd"
let output2 = []
for(let i=input1.length-1;i>=0;i--) {
    if(input1[i]==="+"||input1[i]==="-"||input1[i]==="*"||input1[i]==="/") {
        let op1 = output2.pop()
        let op2 = output2.pop()
        let temp = "(" + op1 + input1[i] + op2 + ")"
        output2.push(temp)
    }
    else {
        output2.push(input1[i])
    }
}
console.log(...output2)

// Question-8
const input8="[(){}[]()]"
const groups ={'[':']','{':'}','(':')'}
const input9=[]
for(let i=0;i<input8.length;i++){
    let y=input8[i]
    if(y==='[' || y==='{' || y==='('){
        input9.push(y)
    }
    else {
        let lastone = input9[input9.length-1]
        if(groups[lastone]==y){
            input9.pop()
        }
    }
}
if(input9.length===0){
    console.log("balanced ")
}
else{
    console.log("not balanced")
}

// Question-9
const input7=[8,4,5,6,2,7,9,3,1]
const arr7=[]
while(input7.length) {
    let data = input7.pop()
    arr7.push(data)
}
console.log(...arr7)

// Question-10
const input10=[5,9,7,8,3,1,2,15,14]
let min=input10[0]
while(input10.length) {
    let a= input10.pop()
    if(min > a) {
        min=a
    }
}
console.log(min)
