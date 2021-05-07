# possezzed
all my code challenges solved(with python)

#CODEWARS CHALLENGES

"""
def song_decoder(song):
#ASSIGN SONG TO A VAR SO WE CAN REPLACE ALL "WUB" FOR WHITESPACE
    txt = song.replace("WUB", " " )
#THEN WE PULL OUT ANY WHITESPACE LEFT BY THE REPLACE METHOD
    whitespace = txt.strip()
#AT LAST IF BY ANY CHANCE THE ARE MULTIPLE WHITESPACE, I USED JOIN and split to format to 1 whitespace per letter
    return ' '.join(whitespace.split())

print(song_decoder("AWUBBWUBC"), "A B C","WUB should be replaced by 1 space")
print(song_decoder("AWUBWUBWUBBWUBWUBWUBC"), "A B C","multiples WUB should be replaced by only 1 space")
print(song_decoder("WUBAWUBBWUBCWUB"), "A B C","heading or trailing spaces should be removed")
"""

"""
#GET MIDDLE CHARACTER

def get_middle(s):
    return s[(len(s)-1)//2:(len(s)+2)//2]


print(get_middle("middle"),"dd")
"""
"""
#disemvowel a string using a for loop

def disemvowel(string):
    for i in "aeiouAEIOU":
        string = string.replace(i,"")
    return string
print(disemvowel("this is aweosme"), "ths s wsm")

def disemvowel(s):
    return s.translate(None, "aeiouAEIOU")

def disemvowel(string):
    return "".join(c for c in string if c.lower() not in "aeiou")
"""
"""
#FILTERING A LIST OF INTS AND STRINGS

def filter_list(l):
    for x in l[:]:
        if isinstance(x, str):
            l.remove(x)
    return l



#filter_list([1,2,'a','b']) == [1,2]
#filter_list([1,'a','b',0,15]) == [1,0,15]
#filter_list([1,2,'aasf','1','123',123]) == [1,2,123]
"""


"""
def array_diff(a, b):
  while a is not b:
    for x in a:
      
print(array_diff([1,2,2], [1]), [2,2], "a was [1,2,2], b was [1], expected [2,2]")
"""
"""
#List of Lists

def open_or_senior(data):
#create and empty list to store the result at the end
  lst= []
#iterate through data list of lists
  for i in data:
#if iterable its more or equal than 55 and iterable its more than 7 
      if i[0] >= 55 and i[1]>7:
#then print a list by appendding our list var 
        lst.append('Senior')
#else print a list by appendding our list var 
      else:
        lst.append('Open')
  return lst
  
print(open_or_senior([[18, 20],[45, 2],[61, 12],[37, 6],[21, 21],[78, 9]]))

#ONE LINE ANSWER

def openOrSenior(data):
  return ["Senior" if age >= 55 and handicap >= 8 else "Open" for (age, handicap) in data]

#isogram
def is_isogram(string):
    clean_word = string.lower()
    letter_list = []
    for letter in clean_word:
        if letter.isalpha():
            if letter in letter_list:
                return False
            letter_list.append(letter)
    return True
        
def is_isogram(string):
  lower= string.lower()
  for l in lower:
    if lower.count(l) > 1: return False
  return True
  
def is_isogram(string):
    return len(string) == len(set(string.lower()))
"""
"""
#ENDS WITH
def solution(string, ending):
  return string.endswith(ending)



print(solution('abc', 'bc'))
print(solution('abc', 'd'))
"""
"""
#DIRECTIONS REDUCTION
def dirReduc(arr):
    dict = {"NORTH": "SOUTH","SOUTH":"NORTH","EAST":"WEST","WEST":"EAST"}
    res = []
    for i in arr:
        if res and dict[i] == res[-1]:
            res.pop()
        else:
            res.append(i)
    return res

a = ["NORTH", "SOUTH", "SOUTH", "EAST", "WEST", "NORTH", "WEST"]
test.assert_equals(dirReduc(a), ['WEST'])
u=["NORTH", "WEST", "SOUTH", "EAST"]
test.assert_equals(dirReduc(u), ["NORTH", "WEST", "SOUTH", "EAST"])

"""
""""
for item in arr:
        if arr.count(item) == 1:
            return item

"""
"""
import re

def sum_digits(number):
    new = [int(i) for i in str(number)]
    res = re.findall('[-+]?\d+', new)
    return res

#print(sum_digits(-32), 5)
print(sum_digits(10), 1)


ANAGRAM
# write the function is_anagram
def is_anagram(test, original):
    if (sorted(test.lower())== sorted(original.lower())):
        return True
    else:
        return False
"""
"""
def max_sequence(arr):
  iter_items = iter(arr) # -2 1 etc 
  try:
    temp_sum = next(iter_items) # next iter item in arr
  except StopIteration:
    temp_sum = 0
  max_sum = temp_sum
  for item in iter_items:
    temp_sum = max(temp_sum + item, item)
    max_sum = max(temp_sum, max_sum)
  return max(max_sum, 0)

#which is O(N) in time and O(1) in memory(complexity)

print(max_sequence([]), 0)
print(max_sequence([-2, 1, -3, 4, -1, 2, 1, -5, 4]), 6)

"""
