<details>
<summary>Click me to reveal the `<details>` ↓</summary>
<ul><li>This is the python to generate an `Int` sum:</li></ul>

```python
# This program adds two numbers

num1 = 1.5
num2 = 6.3

# Add two numbers
sum = num1 + num2

# Display the sum
print('The sum of {0} and {1} is {2}'.format(num1, num2, sum))
```
<ul><li>And here's how you present it as a `.mustache` file:</li></ul>

```json
{
  "sum" : 7.8
}
```
```html
<html>
  <body>
    <p>The final amount is {{sum}}</p>
  </body>
</html>
```
</details>
