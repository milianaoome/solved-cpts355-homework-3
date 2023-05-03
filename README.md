Download Link: https://assignmentchef.com/product/solved-cpts355-homework-3
<br>
<h1>1.(Dictionaries)</h1>

<h2>a)  sumSales(d) –</h2>

Assume that you have an online sales business and you sell products on Amazon, Ebay, Etsy, etc. and  you keep track of your daily sales (in $) for each online store. You maintain the log of your sales in a Python dictionary as follows:

{‘Amazon’:{‘Mon’:30,’Wed’:100,’Sat’:200},’Etsy’:{‘Mon’:50,’Tue’:20,’Wed’:25,’F ri’:30},’Ebay’:{‘Tue’:60,’Wed’:100,’Thu’:30},’Shopify’:{‘Tue’:100,’Thu’:50,’Sa t’:20}}

The keys of the dictionary are the online stores and the values are the dictionaries which include the total sales on different days of the week. Note that if there are no sales in a particular store during the week, that store will not appear in the dictionary.




Define a function, <strong>sumSales(d) </strong>which adds up the amount of sales you made on each day of the week and returns the summed values as a dictionary. Note that the keys in the resulting dictionary should be the days of the week and the values should be the total amount of sales (in $) you made on that day. <strong>sumSales</strong> will return the following for the above dictionary:

{‘Fri’: 30, ‘Mon’: 80, ‘Sat’: 220, ‘Thu’: 80, ‘Tue’: 180, ‘Wed’: 225}




(<em><u>Important note</u></em>: Your function should not hardcode the store names and the days of the week. It should simply iterate over the keys that appear in the given dictionary and should work on any dictionary with arbitrary store names and days of the week)




You can start with the following code:  def sumSales(d):     #write your code here

<strong> </strong>

<h2>b) sumSalesN(L)</h2>

Now assume that you kept the log of sales for several weeks and stored the sales data as a list of dictionaries. This list includes a dictionary for each week you recorded your log. Assuming you kept the log for N weeks, your list will include N dictionaries.




Define a function sumSalesN which takes a list of log dictionaries and returns a dictionary which includes the total amount of sales on each day of the week. Your function definition should use the Python map and reduce functions as well as the sumSales function you defined in part(a).  You will need to define an additional helper function to combine dictionaries.

Example:

Assume you have recorded your log for 3 weeks only.

[{‘Amazon’:{‘Mon’:30,’Wed’:100,’Sat’:200},’Etsy’:{‘Mon’:50,’Tue’:20,’Wed’:25,’ Fri’:30},’Ebay’:{‘Tue’:60,’Wed’:100,’Thu’:30},’Shopify’:{‘Tue’:100,’Thu’:50,’S at’:20}},{‘Shopify’:{‘Mon’:25},’Etsy’:{‘Thu’:40, ‘Fri’:50},

‘Ebay’:{‘Mon’:100,’Sat’:30}},

{‘Amazon’:{‘Sun’:88},’Etsy’:{‘Fri’:55},’Ebay’:{‘Mon’:40},’Shopify’:{‘Sat’:35}} ]

For the above dictionary sumSalesN will return:

{‘Fri’: 135,’Mon’:245,’Sat’:285,’Sun’: 88,’Thu’: 120,’Tue’:180,’Wed’:225}




(The items in the dictionary can have arbitrary order.)

<h1>2. (Dictionaries and Lists)</h1>

<strong> </strong>

<h2>a) searchDicts(L,k)–</h2>

Write a function searchDicts that takes a list of dictionaries L and a key k as input and checks each dictionary in L starting from the end of the list. If k appears in a dictionary, searchDicts returns the value for key k. If k appears in more than one dictionary, it will return the one that it finds first (closer to the end of the list).

For example:

L1 = [{“x”:1,”y”:True,”z”:”found”},{“x”:2},{“y”:False}]

searchDicts(L1,”x”) returns 2 searchDicts(L1,”y”) returns False searchDicts(L1,”z”)  returns   “found”

searchDicts(L1,”t”) returns None




You can start with the following code:  def searchDicts(L,k):

#write your code here

<h2>b) searchDicts2(tL,k)</h2>

Write a function searchDicts2 that takes a list of tuples (tL) and a key k as input. Each tuple in the input list includes an integer index value and a dictionary. The index in each tuple represent a link to another tuple in the list (e.g. index 3 refers to the 4<sup>th</sup> tuple, i.e., the tuple at index 3 in the list)  searchDicts2 checks the dictionary in each tuple in tL starting from the end of the list and following the indexes specified in the tuples.  For example, assume the following:

[(0,d0),(0,d1),(0,d2),(1,d3),(2,d4),(3,d5),(5,d6)]

0       1      2      3      4      5      6

The searchDicts2 function will check the dictionaries d6,d5,d3,d1,d0 in order (it will skip over d4 and d2) The tuple in the beginning of the list will always have index 0.

It will return the first value found for key k. If k is couldn’t be found in any dictionary, then it will return None.




For example:

L2 = [(0,{“x”:0,”y”:True,”z”:”zero”}),

(0,{“x”:1}),

(1,{“y”:False}),

(1,{“x”:3, “z”:”three”}),

(2,{})]

searchDicts2 (L2,”x”) returns 1 searchDicts2 (L2,”y”) returns False searchDicts2 (L2,”z”)  returns “zero”

searchDicts2 (L2,”t”) returns None




(<em><u>Note</u></em>: I suggest you to provide a recursive solution to this problem.

<em><u>Hint</u></em>: Define a helper function with an additional parameter that hold the list index which will be searched in the next recursive call.)

You can start with the following code:

def searchDicts2(L,k):

#write your code here

<h1>3.  (List Comprehension)  busStops(buses,stop)</h1>

Pullman Transit offers many bus routes in Pullman. Assume that they maintain the bus stops for their routes as a dictionary. The keys in the dictionary are the bus route names and the values are the stops for the bus routes (see below for an example).




routes = {

“Lentil”: [“Chinook”, “Orchard”, “Valley”, “Emerald”,”Providence”, “Stadium”, “Main”,

“Arbor”, “Sunnyside”, “Fountain”, “Crestview”, “Wheatland”, “Walmart”, “Bishop”, “Derby”, “Dilke”],

“Wheat”: [“Chinook”, “Orchard”, “Valley”, “Maple”,”Aspen”, “TerreView”, “Clay”,

“Dismores”, “Martin”, “Bishop”, “Walmart”, “PorchLight”, “Campus”],

“Silver”: [“TransferStation”, “PorchLight”, “Stadium”, “Bishop”,”Walmart”, “Shopco”, “RockeyWay”],

“Blue”: [“TransferStation”, “State”, “Larry”, “TerreView”,”Grand”, “TacoBell”,

“Chinook”, “Library”],

“Gray”: [“TransferStation”, “Wawawai”, “Main”, “Sunnyside”,”Crestview”, “CityHall”, “Stadium”, “Colorado”]

}

Write a function busStops that takes a dictionary (buses) similar to the above dictionary and a stop name (stop) as input. The function returns the list of the buses which stop at the given stop.  For example:

busStops(routes,”Stadium”) returns  [‘Lentil’, ‘Silver’, ‘Gray’]

<strong>You should implement your function using “list comprehension” in 2 lines. A solution that doesn’t use list comprehension will be worth half of the points. </strong>




You should not hardcode route names and the bus stop names in your function.  You can start with the following code:




def busStops (buses,stop):

#write your code here

<h2>4. (Lists) palindromes(s)</h2>

Write a function, palindromes, which takes a string as input and returns a list of the unique palindromes that appear in the input string. You may assume that the input string doesn’t have any ‘space’ characters and all characters are lowercase. The strings in the output should be sorted alphabetically.

<em>(Palindrome is a string that reads the same backward as forward, e.g., madam or kayak). </em>

palindromes (‘cabbbaccab’) returns

[‘abbba’, ‘acca’, ‘baccab’, ‘bb’, ‘bbb’, ‘cabbbac’, ‘cc’]

palindromes (‘ bacdcabdbacdc’) returns  [‘abdba’, ‘acdca’, ‘bacdcab’, ‘bdb’, ‘cabdbac’, ‘cdc’, ‘cdcabdbacdc’,

‘dcabdbacd’]

palindromes (‘ myracecars’) returns

[‘aceca’, ‘cec’, ‘racecar’]




You can start with the following code:

def palindromes(S):

#write your code here

<h1>5. Iterators</h1>

<h2>a) interlaceIter()– 20%</h2>

Create an iterator that represents the interlaced sequence of values from two input iterators. The iterator will iterate over the values in the input sequences and return the next element from those  interchangeably.  The iterator should stop when it reaches the end of either of the input sequences. It should truncate the rest of the elements in the longer sequence. If both input sequences are infinite, the interlaceIter will return an infinite sequence as well.




For example:

iSequence = interlaceIter(iter([1,2,3,4,5,6,7,8,9]),iter(“abcdefg”)) iSequence.__next__()   # returns 1 iSequence.__next__()   # returns ‘a’ iSequence.__next__()   # returns 2 for item in iSequence:

print(item)

# prints the rest of the items, i.e., ‘b’,3,’c’,4,’d’,5,’e’,6,’f’,7,’g’

You can start with the following code:




class interlaceIter():     #write your code here

<strong> </strong>

<h2>b) typeHistogram(it,n)–</h2>

Define a function typeHistogram that takes an iterator “it” (representing a sequence of values of different types) and builds a histogram showing how many values of each type appears in the next n elements in the sequence. <strong>typeHistogram</strong> should return a list of tuples, where each tuple includes the type names and the number of times that type appears in the next n elements.  For example:

typeHistogram(iSequence,5)  # returns [(‘int’, 3), (‘str’, 2)] typeHistogram(iSequence,5)  # returns [(‘str’, 3), (‘int’, 2)] typeHistogram(iSequence,5)  # returns [(‘int’, 2), (‘str’, 2)] typeHistogram(iSequence,5)  # returns []




(<u>Note</u>: You can use the Python “type” function to get the type name of a value. For example: type(“CptS355”).__name__   returns ‘str’ type(10).__name__   returns ‘int’




You can start with the following code: def typeHistogram (it,n):

<strong>    </strong>#write your code here

<h1>Testing your functions</h1>

We will be using the unittest Python testing framework in this assignment.  See  <u>https://docs.python.org/3/library/unittest.html</u> for additional documentation.




The file HW3SampleTests.py provides some sample test cases comparing the actual output with the expected (correct) output for some problems.  This file imports the HW3 module (HW3.py file) which will include your implementations of the given problems.

Rename the HW3SampleTests.py file as HW3Tests.py and add your own test cases in this file. You are expected to add <strong>at least 2 more test cases</strong> for each problem. Make sure that your test inputs cover all boundary cases. Choose test input different than those provided in the assignment prompt.

In Python unittest framework, each test function has a “test_” prefix. To run all tests, execute the following command on the command line.

python -m unittest HW3SampleTests

You can run tests with more detail (higher verbosity) by passing in the -v flag:

python -m unittest -v HW3SampleTests




If you don’t add new test cases you will be deduced at least 5% in this homework.

<h2>Main Program</h2>

In this assignment, we simply write some unit tests to verify and validate the functions. If you would like to execute the code, you need to write the code for the “main” program. Unlike in C or Java, this is not done by writing a function with a special name. Instead the following idiom is used. This code is to be written at the left margin of your input file (or at the same level as the def lines if you’ve indented those.

<strong> if</strong> __name__ == ‘__main__’:

…code to do whatever you want done…


