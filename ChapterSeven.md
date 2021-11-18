# Chapter Seven Notes

Flexible structure for storing a sequence of values that are all of the same type
 - element: One value in an array
 - index: A zero-based integer to access an element from an array

 - Arrays are objects which means they must be constructed
 - The general syntax for declaring and constructing an array is:
`[<element type>[]<name>=new<element type>[<length>];`
 - An array is declared by:
`double[] temperature;  // declared with type followed by []`


## Array Examples

```
int[] intArray = new int[100]; 
declares an array of 100 integers initialized to 0

double[] temperature = {4.5, 16.7, 3.1, 25.0, 6};
...array of 5 doubles with initialized values

String[] strWeekDayArr = {“Mon”,”Tue”,”Wed”,”Thu”,”Fri”};
...array of 5 String objects with initialized values

boolean[] flags = new boolean[25];
...array of 25 booleans initialized to false

Color[] colors = new Color[50];
...array of 50 Color objects

```



## Why use arrays

 - Arrays are easy to work with!!
 - multiple elements using a single variable name
 - elements can be accessed randomly
`int [] myArray = {5,6,7}; `
`myArray[index] 			// access`
`myArray[index] = value;       	// modify`
 - Creating and retrieving data in an array is fast
 - arrays allocate memory in a contiguous location for all of the elements





## Out of bounds

 - Legal indexes: between 0 and the array's length - 1.
 - Reading or writing any index outside this range will throw an ArrayIndexOutOfBoundsException.
```
int[] data = new int[10];
	System.out.println(data[0]);       // okay
	System.out.println(data[9]);       // okay
	System.out.println(data[-1]);      // exception
	System.out.println(data[10]);      // exception
```


## Array Utilities

 - The Arrays class adds utilities for arrays
Must import `java.util.*;`
`int[] newarr = Arrays.copyOf(arr, newsize)` increases size of array
`Arrays.toString(arr)` to print an array
`Arrays.equals(arr1, arr2)` to contain the same elements in the same order

Another way to access elements
```
The for-each loop takes the following general form:
	for (<type> <name> : <array>) {
		<statement>
		<statement>
		…
		<statement>
	} 
```
## Value Semantics
 - Value Semantics
 - Values are copied when assigned, passed as parameters or returned,     
 - All primitive types in Java use value semantics
 - When one variable is assigned to another, its value is copied.
 - Modifying the value of one variable does not affect the others

#### Reference Semantics

 - Reference Semantics allows for sharing of the object
 - When one variable is assigned to another the object is not copied; 
both variables refer to the same object


 - Reference Semantics and Arrays
`double[] temperature = {2.0, 6.5, 8.4}; `    
 - two different values are stored in memory
 - the array which appears on the right
 - the variable called temperature    
 - When an object (eg. an array) is passed as a parameter the parameter refers to the same object.  
 - Modifying the object through the method parameter modifies the original object


```
public static void main(String[] args) {
	    int[] iq = {126, 167, 95};
	    increase(iq);
	    System.out.println(Arrays.toString(iq));
	}

	public static void increase(int[] a) {
	    for (int i = 0; i < a.length; i++) {
	        a[i] = a[i] * 2;
	    }
	}

```



Output:
	`[252, 334, 190]`
	
	


## Example Flowcharts

![examples](FlowchartsExamples.PNG)


## Tallying


 - Simply keeping a count for various pieces of information
 - Used to analyze captured data from any source, experiment, etc.
 - Example: counting unique occurrences of a word, daily temp, event etc.

```
// assume n = 669260267
	int[] counts = new int[10];
	while (n > 0) {
	    // pluck off a digit and add to proper counter
	    int digit = n % 10;
	    counts[digit]++;
	    n = n / 10;
	}
```

![Simply tally flowchart](SimpleTally.PNG)

```
private static int[] buildArray(int arraySize) {
   int[] largeArray = new int[arraySize];
   int index = 0;
   while (index < arraySize) {
       int value = 20 + (int)(Math.random() * ((105 - 20) + 1));
       largeArray[index] = value;
       index++;
   }
   return largeArray;
}
```

# Multi - Dimensional Arrays


 - An array of arrays..
 - Elements access via multiple integer indexes

	`int []; `
	`int [][];`	Two dimensional array of ints
`int [][][];` Three dimensional array of ints

`Double temps[][] = new double [3][5];`
`Double temps[][] = new double [3][5];`

`temps[1][4] = 4.9;     // 4th value of second row`

`temps[0][2] = 2.1;     // 3rd value of first row`

 - Number of rows:
 - temps.length
 - Length of row 0 (# columns):
 - temps[0].length

To access elements in a multi-dimensional with for loop
```
int [][] myArray = new int [2][[3];
for (int row = 0; row < myArray.length; row++) {      // loop each row
for (int col =0; col < myArray[row].length; col++) {     // loop each column
<statement>
     }
}
```

To print contents with Array utilities
`Arrays.deepToString()`
`Arrays.toString[myArray]`

```
private static int [][] build2DArray(int rowCount, int colCount){
   int [][] twoDArray = new int[rowCount][colCount];
   for (int row = 0; row < rowCount; row++){
       for (int column = 0; column < colCount; column++){
           twoDArray[row][column] = 1+(int)(Math.random()*((9-1)+1));
       }
   }
   return  twoDArray;
}

```

# Test Prep Summary

 - Know how to create and access elements in a linear array:
 - for, while and for-each loops
`[<element type> [] <name> = new <element type> [<length>];`
`[<element type> [] <name> = {<element> ,  <element>, <element>  };`
 - Know how to create and access elements in a 2D array:
 - nested loops etc.
 - Arrays contain homogenous elements (primitive data types and objects)
 - fixed length structure
 - Reference vs. Value Semantics
 - implications for assignment, use as parameters 
 - must be able to trace code that spans multiple methods using primitives & arrays and differentiate their behavior as they are manipulated
 - Know how to use linear and 2D arrays to solve problems..
 - count / sum / min & max / tallying


