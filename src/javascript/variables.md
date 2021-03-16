---
layout: layouts/childpage.njk
title: Javascript Variables
templateClass: tmpl-home
eleventyNavigation:
  key: Variables
  parent: Javascript
  order: 1
---

<div class="container mt-5">
  <h1>Basic Javascript Tasks for Variables</h1>

  <p>Open the console to view the results</p>

  <h2>Javascript code used</h2>
  <pre>
/* trying out different ways of outputting messages 
  This is a multiline comment
*/
// alert message
alert('Alex is cool - well maybe, maybe not');
// write message to console
console.log('Alex is cool - well maybe, maybe not')
// append message to body tag - not a good idea really!
document.write('Alex is cool - well maybe, maybe not')
  </pre>
  <pre>
var message = "I am fed up with Alex is cool";
alert(message);
  </pre>

  <pre>
var a = 10;
var b = 5;
var sum;
sum = a+b;
console.log('addition ' + sum);
sum = a-b;
console.log('subtraction ' + sum);
sum = a*b;
console.log('multiply ' + sum);
sum = a/b;
console.log('divide ' + sum);
sum = a%b;
console.log('modulus ' + sum);
a = 21.3
sum = a%b;
console.log('modulus ' + sum);
  </pre>

  <pre>
var firstName = 'Elizabeth';
var lastName = 'Guest';
var fullName = firstName + ' ' + lastName;
console.log(fullName);
  </pre>

  <pre>
/* 
  Bill with tip programme
  */
var pre_tip_total = 35.86;
var one_percent = pre_tip_total / 100;
var tip_percent = 15;
var tip_amount = one_percent * tip_percent;
var tip_amount2 = pre_tip_total * tip_percent / 100;
console.log(tip_amount + ' ' + tip_amount2);
//round to two decimal places - turns it into a string
tip_amount = tip_amount.toFixed(2)
var bill_total = parseFloat(pre_tip_total) + parseFloat(tip_amount);
console.log(bill_total);
var str_Message = 'Your food bill was £' + pre_tip_total + 
                  ', you have tipped ' + tip_percent + 
                  '% which equals £' + tip_amount + 
                  ', bringing your total bill to £' + bill_total;
console.log(str_Message);
  </pre>
</div>

<script>
  /* trying out different ways of outputting messages 
     This is a multiline comment
  */
    // alert message
    alert('Alex is cool - well maybe, maybe not');
    // write message to console
    console.log('Alex is cool - well maybe, maybe not')
    // append message to body tag - not a good idea really!
    document.write('Alex is cool - well maybe, maybe not')

    var message = "I am fed up with Alex is cool";
    alert(message);

    var a = 10;
    var b = 5;
    var sum;
    sum = a+b;
    console.log('addition ' + sum);
    sum = a-b;
    console.log('subtraction ' + sum);
    sum = a*b;
    console.log('multiply ' + sum);
    sum = a/b;
    console.log('divide ' + sum);
    sum = a%b;
    console.log('modulus ' + sum);
    a = 21.3
    sum = a%b;
    console.log('modulus ' + sum);

    var firstName = 'Elizabeth';
    var lastName = 'Guest';
    var fullName = firstName + ' ' + lastName;
    console.log(fullName);

    /* 
      Bill with tip programme
      */
    var pre_tip_total = 35.86;
    var one_percent = pre_tip_total / 100;
    var tip_percent = 15;
    var tip_amount = one_percent * tip_percent;
    var tip_amount2 = pre_tip_total * tip_percent / 100;
    console.log(tip_amount + ' ' + tip_amount2);
    //round to two decimal places - turns it into a string
    tip_amount = tip_amount.toFixed(2)
    var bill_total = parseFloat(pre_tip_total) + parseFloat(tip_amount);
    console.log(bill_total);
    var str_Message = 'Your food bill was £' + pre_tip_total + 
                      ', you have tipped ' + tip_percent + 
                      '% which equals £' + tip_amount + 
                      ', bringing your total bill to £' + bill_total;
    console.log(str_Message);

</script>