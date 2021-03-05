---
layout: post
title: GPT does "the work"
date: 2021-03-05 12:55:35 -0500
category: ML
author: David Boyd
categories: [Audit, AI, ML]
summary: Summary of the article
javascript: 2021-03-05-dtw.js
---

# *Deep AI models like GPT-3 can do 'the work' in Finance*

<!--more-->
For observers outside of AI research, the GPT-3 Deep Learning model from the team at OpenAI appears pretty shocking. Put simply, this is an AI model which has read and "learned" from a corpus of approx 45 TB in raw text; the equivalent of close to 1 trillion pages of text.  Since release, there have been examples of GPT coding javascript sites based on descriptions[^1], coming up with SQL queries[^2], and visualizations of data based on plain english requests [^3].

Could this AI model could perform knowledge work in my industry? Work which requires critical process understanding, and analytical reasoning. Work, within financial consultancy, which would ordinarily involve a deep understanding of business processes along with accounting and finance.

## Can it do "the work"?

 With this critical question, I put the GPT model to the following test [^4]: Could an AI model perform the following sorts of processes?:

1. Read a description of a financial process narrative, and determine what the risk is.
2. Given a specific risk, design a process to test it.
3. Given a loose test description, propose a SQL query to technically execute the test.
4. Given technical test results, summarize these into a formalized written finding and recommendation.

The following examples show the results of a textual prompt provided to the model, (i.e. the input), followed by the model's response:

### Highlighting a risk

Given a Description, describe the risk:

<div id="termynal1" data-termynal data-ty-typeDelay="40" data-ty-lineDelay="700" data-ty-startDelay="2000">
    <span data-ty="input" data-ty-prompt=">">Description: We observed the process by which cash was accepted from customers, Although the cash register was utilized receipts were not provided to customers.</span>
    <span data-ty="input" data-ty-prompt=">">Risk:</span>
    <span data-ty="progress" data-ty-progressChar="·"></span>
    <span data-ty>The potential for a cash register failure is increased by the nature of the product. The cash register is used for several purposes including receiving cash from customers, paying bills, and maintaining inventory. If a cash register fails, the customer may experience delays in receiving their order and/or payment.</span>
</div>

### Designing a test

Given an Account and risk, design a process to test:

<div id="termynal2" data-termynal data-ty-typeDelay="40" data-ty-lineDelay="700" data-ty-startDelay="4000">
    <span data-ty="input" data-ty-prompt=">">Account: Revenue</span>
    <span data-ty="input" data-ty-prompt=">">Risk: During a review of cash register cash reciepts, there was a risk that cash was not accepted from customers.</span>
    <span data-ty="input" data-ty-prompt=">">Audit Assertion: Completeness & Accuracy</span>
    <span data-ty="input" data-ty-prompt=">">Planned Audit Procedures:</span>
    <span data-ty="progress" data-ty-progressChar="·"></span>
    <span data-ty>1. Reviewed all records of cash registers to determine whether all cash registers were operational, including both cash registers and counters.</span>
    <span data-ty>2. Examined all records of cash registers, counters and receipts to determine if cash was accepted.</span>
    <span data-ty>3. Obtained records from cash registers, counters and receipts.</span>
    <span data-ty>4. Conducted an audit of the cash registers, counters and receipts.</span>
    <span data-ty>5. Collected information on cash registers, counters and receipts.</span>
    <span data-ty>6. Reviewed records to determine if cash was accepted at all cash registers and counters.</span>
</div>

### Designing a query

Given a description, design a technical test:

<div id="termynal3" data-termynal data-ty-typeDelay="40" data-ty-lineDelay="700" data-ty-startDelay="6000">
    <span data-ty="input" data-ty-prompt=">">Given a database dbo.SalesOrderHeader, provide a SQL query to return the top 10 highest sales orders with a total of $5,000 or more.</span>
    <span data-ty="progress" data-ty-progressChar="·"></span>
    <span data-ty>-- CREATE TABLE dbo.SalesOrderHeader (OrderID int, OrderDateTime datetime, ProductID int, ProductName nvarchar(30), TotalAmount money, TotalAmountQuantity money) -- DROP TABLE dbo.SalesOrderHeader</span>
    <span data-ty>The following query will return the top 10 highest sales orders with a total of $5,000 or more.</span>
    <span data-ty>SELECT TOP 10 * FROM dbo.SalesOrderHeader WHERE OrderID = 10 AND OrderDateTime BETWEEN '2012-01-01' AND '2012-01-02' ORDER BY TotalAmountQuantity DESC;</span>
</div>

### Report on findings

Using a findings and then extrapolating findings:

<div id="termynal4" data-termynal data-ty-typeDelay="40" data-ty-lineDelay="700" data-ty-startDelay="8000">
    <span data-ty="input" data-ty-prompt=">">Test Results: Out of 25 Samples 2 Receipts were noted where cash was not deposited into the bank account.</span>
    <span data-ty="input" data-ty-typeDelay="100" data-ty-prompt=">">Audit Finding and Recommendation:</span>
    <span data-ty="progress" data-ty-progressChar="·"></span>
    <span data-ty>The Company should re-examine its verification process for cash deposits and notes, including an expanded focus on the verification of the cashier's receipt of the note.</span>
    <span data-ty>Recommendation #2: The Company should develop a risk-based approach to cash handling and deposit requirements for deposits and notes that includes a review of the frequency of cash deposits and the frequency of cash withdrawal from the bank account.</span>
    <span data-ty>Recommendation #3: The Company should expand the frequency of the verification process for cash deposits and notes to include a review of the verification of the cashier's receipt of the note.</span>
</div>

## Opportunities

Overall this is pretty impressive, and a pretty huge leap from simple autocorrect style algorithms. 

The answers from "one-shot" responses are what you'd expect from an entry level professional and immediately, these models offer a potential of massive leap forward in supervised tasks, Think: Spell/Grammar Check on steroids.

Let me know if you have any thoughts or feedback on twitter.

### _References:_

[^1]: [@sharifshameem/](https://twitter.com/sharifshameem/status/1282676454690451457?s=20)
[^2]: [@aquariusacquah](https://twitter.com/aquariusacquah/status/1284706786247880705?s=2)
[^3]: [@aquariusacquah](https://twitter.com/aquariusacquah/status/1285415144017797126?s=20)
[^4]: Model details above were extracted based on the medium sized GPT-2 Model with no fine tuning applied except for a preliminary prompt.

<!-- Termynal lazy_loading code -->

<script src="/assets/js/jquery-3.5.1.slim.min.js"></script>
<script src="/assets/js/termynal.js"></script>

<script>
var termynal1 = new Termynal('#termynal1', { startDelay: 600, typeDelay:40, lineDelay:700, noInit: 'true'});
var termynal2 = new Termynal('#termynal2', { startDelay: 600, typeDelay:40, lineDelay:700, noInit: 'true' });
var termynal3 = new Termynal('#termynal3', { startDelay: 600, typeDelay:40, lineDelay:700, noInit: 'true' });
var termynal4 = new Termynal('#termynal4', { startDelay: 600, typeDelay:40, lineDelay:700, noInit: 'true' });
var termynal1_fired = false;
var termynal2_fired = false;
var termynal3_fired = false;
var termynal4_fired = false;

$(window).scroll(function() {
  if(($(window).scrollTop() + $(window).height() > $('#termynal1').first().position().top) && termynal1_fired == false) {
       termynal1.init();
       termynal1_fired = true;
   };
    if(($(window).scrollTop() + $(window).height() > $('#termynal2').first().position().top) && termynal2_fired == false) {
       termynal2.init();
       termynal2_fired = true;
   };
     if(($(window).scrollTop() + $(window).height() > $('#termynal3').first().position().top) && termynal3_fired == false) {
       termynal3.init();
       termynal3_fired = true;
   };
     if(($(window).scrollTop() + $(window).height() > $('#termynal4').first().position().top) && termynal4_fired == false) {
       termynal4.init();
       termynal4_fired = true;
   };
});

</script>