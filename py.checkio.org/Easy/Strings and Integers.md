# Strings and Integers
Решено 97% задач данной локации. Осталась всего одна "Excel Column Number"

Acceptable Password I
```python
def is_acceptable_password(password: str) -> bool:
    return True if len(password)>6 else False
```
All Permutations
```python
from collections.abc import Iterable
from itertools import *

def string_permutations(s: str) -> Iterable[str]:
    arr = []
    for i in permutations(s):
        sum = ''.join(i)
        arr.append(sum)
    print(arr.sort())
    return arr
```
All Upper I
```python
def is_all_upper(text: str) -> bool:
    return True if text == text.upper() else False
```
Armstrong Number Checking
```python
def is_armstrong(num: int) -> bool:
    numbers = []
    sum = 0
    for i in range(len(str(num))):
        numbers.append(int(str(num)[i]))
    for j in range(len(numbers)):
        sum += numbers[j]**len(numbers)
    if sum == num:
        return True
    else:
        return False
```
Backward String
```python
def backward_string(val: str) -> str:
    return val[::-1]
```
Beginning Zeros
```python
def beginning_zeros(a: str) -> int:
    if a[0] != '0':
        return (0)
    else:
        for i in range(len(a)): 
            if a[i] == '0':
                i += 1
            else:
                break
        return i
```
Between Markers (simplified)
```python
def between_markers(text: str, start: str, end: str) -> str:
    return (text[int(text.find(start)) + 1:int(text.find(end))])
```
Bird Language
```python
VOWELS = "aeiouy" 
def translate(phrase):
    i = 0
    new_phrase = ''
    while i < len(phrase):
        if phrase[i] == ' ':
            new_phrase += phrase[i]
            i += 1
        elif phrase[i] in VOWELS:
            new_phrase += phrase[i]
            i += 3
        else:
            new_phrase += phrase[i]
            i += 2
    return new_phrase
```
Conversion from CamelCase
```python
def from_camel_case(name: str) -> str:
    for world in name:
        if world.isupper():
            name = name.replace(world, '_' + world.lower())
    return name.strip('_')
```
Conversion into CamelCase
```python
def to_camel_case(name: str) -> str:
    return name.replace('_', ' ').title().replace(' ', '')
```
Convert Date
```python
def convert_date(date: str) -> str:
    dd = int(date[0] + date[1])
    mm = int(date[3] + date[4])
    yyyy = int(date[6:10])
    date_convert = ('-'.join(date.split('/')[::-1]))
    if len(date_convert) != 10:
        return "Error: Invalid date."
    elif 12 < mm or 31 < dd or yyyy < 1900 or yyyy > 2100:
        return "Error: Invalid date."
    elif mm in (4,6,9,11) and dd > 30:
        return "Error: Invalid date."
    elif mm == 2 and dd > 29:
        return "Error: Invalid date."
    elif (yyyy == 1900 or yyyy == 2100 or yyyy % 4 != 0) and mm == 2 and dd > 28:
        return "Error: Invalid date."
    else:
        return date_convert
```
Convert To Title Case
```python
def to_title_case(sentence: str) -> str:
    return sentence.lower().title()
```
Correct Sentence
```python
def correct_sentence(text: str) -> str:
    if text[-1] != '.':
        text = text + '.'
    return text[0].upper() + text[1:]
```
Count Divisibles in Range (simplified)
```python
def count_divisible(n: int, k: int) -> int:
    count = 0
    for number in range (1, n + 1):
        if number % k == 0:
            count += 1
    return count
```
Count Substring Occurrences
```python
def count_occurrences(main_str: str, sub_str: str) -> int:  
    if len(sub_str) % 2 == 0:
        num = int(len(sub_str)/2)
        for i in range(num):
            if sub_str[i] == sub_str[num + i]:
                sub_str_c = sub_str[0:num + i]
                break
        if len(main_str) % len(sub_str_c) == 0:
            number = main_str.lower().count(sub_str_c.lower()) - 1
            return number
    else:
        return main_str.lower().count(sub_str.lower())
```
Count Vowels
```python
def count_vowels(text: str) -> int:
    return sum([1 for x in text.lower() if x in 'aeiou'])
```
Cut Sentence
```python
def cut_sentence(line: str, length: int) -> str:
    if len(line) <= length:
        return line
    elif length == 1:
        return '...'
    else:
        if line[length-1] == ' ':
            return line[:length-1] + '...'
        elif line[length] == ' ':
            return line[:length] + '...'
        else:
            line = line[:length]
            while line[-1] != ' ':
                line = line[:-1]
                if len(line) == 0:
                    break         
            return line[:-1] + '...'
```
Digits Multiplication
```python
def checkio(number: int) -> int:
    a = []
    b = str(number)
    mult = 1
    for i in b:
        if i != '0':
           a.append(int(i)) 
    for j in a:
        mult *= j 
    return mult
```
Empty Function
```python
# write your code here
def func():
    pass
```
End Zeros
```python
def end_zeros(n):
    return 0 if n  % 10 else 1 + (end_zeros(n // 10) if n else 0)
```
Excel Column Number
```python
###########
```
Find Remainder
```python
def find_remainder(dividend: int, divisor: int) -> int:
    return dividend % divisor
```
First Word
```python
def first_word(text: str) -> str:
    word = text.replace('.',' ').replace(',', ' ').split()
    return word[0]
```
First Word (simplified)
```python
def first_word(text: str) -> str:
    word = text.split()
    return word[0]
```
Fizz Buzz
```python
def checkio(num: int) -> str:
    return 'Fizz Buzz' if num % 3 == 0 and num % 5 == 0 else 'Fizz' if num % 3 == 0 else 'Buzz' if num % 5 == 0 else str(num)
```
Fuzzy String Matching
```python
def fuzzy_string_match(str1: str, str2: str, threshold: int) -> bool:
    count = 0
    if 0 < threshold <= max(len(str1), len(str2)):
        for i in range(max(len(str1), len(str2)) - 1):
            if str1[i] == str2[i]:
                count += 1
        if threshold <= count:
            return True
        else: 
            return False
    else: return False
```
Goes Right After
```python
# Taken from mission Goes Right After (simplified)
def goes_after(word: str, first: str, second: str) -> bool:
    a = first + second
    if first in word: 
        word = word[0:word.find(first) + 2]
        if second in word: 
            word = word[0:word.find(second) + 2]
            if a in word: 
                return True
            else: return False
        else: return False
    else: return False
```
Goes Right After (simplified)
```python
def goes_after(word: str, first: str, second: str) -> bool:
    a = first + second
    if a in word:
        return True
    else: return False
```
Integer Sign Determination
```python
def determine_sign(num: int) -> str:
    return "positive" if num > 0 else "negative" if num < 0 else "zero"
```
Is Even
```python
def is_even(num: int) -> bool:
    return True if num % 2 == 0 else False
```
Just Fizz!
```python
def checkio(num: int) -> str:
    return f'{num}'if num%3 != 0 else 'Fizz'
```
Leap Year Checking
```python
def is_leap_year(year: int) -> bool:
    if year % 100 == 0:
        if year % 400 == 0:
            return True
        else: 
            return False
    else:
        if year % 4 == 0:
            return True
        else: 
            return False
```
Longest Common Prefix
```python
def longest_prefix(arr: list[str]) -> str:
    t = ''
    if len(arr) == 1:
        return arr[0]
    elif len(arr) == 2:
        for i in range(min(len(arr[0]),len(arr[1]))):
            if arr[0][i] == arr[1][i]:
                t += arr[0][i]      
        return t
    else:
        for i in range(min(len(arr[0]),len(arr[1]),len(arr[2]))):
            if arr[0][i] == arr[1][i] == arr[2][i]:
                t += arr[0][i]          
            else:
                 break
    return t
```
Longest Substring of Unique Characters
```python
def longest_substr(s:str):
        """
        :type s: str
        :rtype: int
        """
        mx, start, chars = 0, 0, {}
        for i in range(len(s)):
            if s[i] in chars and start <= chars[s[i]]: 
                start = chars[s[i]] + 1
            else: mx = max(mx, i - start + 1)
            chars[s[i]] = i
        return mx
```
Max Digit
```python
def max_digit(value: int) -> int:
    m = value % 10
    value = value // 10
    while value > 0:
        if value % 10 > m:
            m = value % 10
        value = value // 10
    return m
```
Maximum Among Three
```python
def max_of_three(a: int, b: int, c: int) -> int:
    return max(a,b,c)
```
Middle Characters
```python
def middle(text: str) -> str:
    if len(text) % 2 == 0:
        return text[len(text)//2 - 1:len(text)//2 + 1]
    else:
        return (text[len(text)//2])
```
Multiply (Intro)
```python
def mult_two(a: int, b: int) -> int:
    return a*b
```
Number Length
```python
def number_length(value: int) -> int:
    return int(len(str(value)))
```
Number With Exclamation
```python
def factorial(n: int) -> int:
    if n == 0:
        return 1
    else:
        for x in range(1,n):
            n *= x
        return n
```
Perfect Number Checking
```python
def is_perfect(n: int) -> bool:
    numb1 = []
    for i in range(n - 1, 1, -1):
        if (n % i == 0):
            numb1.append(i)
    if n == sum(numb1) + 1:
        return True
    else:
        return False
```
Quadratic Equation Roots
```python
from collections.abc import Iterable
def quadratic_roots(a: int, b: int, c: int) -> Iterable[int | str]:
    answer = []
    D = b**2 - 4*a*c
    if (D > 0) or (D == 0):
        answer.append(((-b + D**0.5)/(2*a)))
        answer.append(((-b - D**0.5)/(2*a)))
    else:
        answer.append(str("No real roots"))
    return answer
```
Rectangle Perimeter
```python
def rectangle_perimeter(length: int, width: int) -> int:
    return 2*(length + width)
```
Replace All Occurrences
```python
def replace_all(mainText: str, target: str, repl: str) -> str:
    mainText = mainText.replace(target, repl)
    return mainText
```
Reverse Integer
```python
def reverse_digits(num: int) -> int:
    if num >= 0:
        y = int(str(num)[::-1])
    else:
        y = -int(str(num)[::-1].replace('-',''))
    return y
```
Sum Numbers
```python
def sum_numbers(text: str) -> int:
    num = []
    text = text.split()
    for n in text:
        if n.isdigit() == True:
            num.append(n)
        else:
            num.append(0)
    return (sum(int(p) for p in num))
```
Sum of Integers
```python
def sum_upto_n(N: int) -> int:
    return (int(N*(1 + N)*0.5))
```
Take and Return Argument
```python
def func(arg):
    return arg
```
The Longest Word
```python
def longest_word(sentence: str) -> str:
    if (sentence == "") or (sentence == " "):
        return ""
    else:
        sentence = sentence.replace('-', '').replace("!", "").split()
        max_s = max(sentence, key = len)
        return max_s
```
The Most Wanted Letter
```python
def checkio(text: str) -> str:
    text = ' '.join([x for x in text if not x.isdigit()])
    word = text.lower().replace('.','').replace(',', '').replace('?', '').replace('!', '').replace('!', '').replace(' ', '').replace('-', '')
    c = dict()
    for letter in word:
        c[letter] = c.get(letter, 0) + 1
    sort_data = sorted(c.items())
    sort_data_dict = dict(sort_data)
    word = max(sort_data_dict.items(), key=lambda item: item[1])[0]
    return word
```
Three Words
```python
def checkio(words: str) -> bool:
    count = 0
    for w in words.split():
        if w.isalpha():
            count += 1
        else:
            count = 0
        if count == 3:
            return True
    return False
```
Variable: Declaration and Value Setting
```python
# write your code here
a = 2
b = 5
```
Variables with Expression Values
```python
# Taken from mission Variable: Declaration and Value Setting
# write your code here
a = 2
b = 5
add, multi = a + b, a * b
```
