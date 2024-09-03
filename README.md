# Mystery Function

I used Programiz as an online compiler.

I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.

What does the `mystery()` function in the following piece of code do? Add your
answer to this markdown file.

```javascript
function mystery(a) {
    if(a.length == 1) return a[0];
    var foo = mystery(a.slice(1, a.length))
    if(foo > a[0]) return foo;
    else return a[0];
}
```
Answer:
The Mystery Function (mystery()) takes an argument 'a' which is an array. If the array is just one element, it will return that one element in the array. Otherwise,
a variable 'foo' is created which recursively calls mystery(), creating a new array sliced at the 2nd value (position 1) and ending at the end of the array. 
Variable foo will continue to be declared recursivley until there is only one element in the array. When there is only one element, no new recurve calls will be made, and the second if-statement will be applicable for each recursive step. This if-statement compares foo to a[0], returning either foo or a[0] depending on which is greater. This happens as many times as the recursion was called (size of input array -1). Essentially, this mystery function will return the greatest value of the array, regardless of size, while using recursion. 

My code with console.log tests:
function mystery(a) {
    if(a.length == 1){ console.log('case1: ' + a[0]); return a[0];}
    console.log('a.slic(1, a.length): ' + a.slice(1, a.length));
    var foo = mystery(a.slice(1, a.length))
    console.log('foo: ' + foo);
    if(foo > a[0]){ console.log('a[0]: ' + a[0]); return foo;
    } else { console.log('case2: '+ a[0]); return a[0];
    }
}
var b = [1, 2, 3, 4,5,6,7];
console.log(mystery(b));

var c = [6,6,5,4,3,2,1];
console.log(mystery(c));

var d =[2];
console.log(mystery(d));
