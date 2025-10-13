# Challange 1 - hash-browns

**Date:** 2025-09-29
**Category:** WEB

## Flag 1
The challange presents us with an sign in page and a link to [CrackStation](https://crackstation.net/).
Upon inspecting the page's Javascript code, we see that the sign in form links to a `check_password` function that hashes the provided password and checks if against a string stored in the code.
This string can be assumed to be the hashed password and, when the string is run through the provided Crackstation site it indeed resolved to a password.

After entering the unhashed password, we are taken to a page with a bouncing 'catch me if you can' element and after instpecting the page data again we can see that the bouncing element calls the function `print_flag` upon being clicked.
So, instead of attempting to click the element, we can manually call the `print_flag()` function in the browser console, causing the 'catch me if you can' to be replaced by the flag.
(You could also just extract the obfuscated flag from the javascript function, but why?)

The displayed flag text can then be captured and submitted.
