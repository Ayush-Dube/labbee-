## 🔸 lab1
### Arrays
- Arrays are a fundamental data structure in Java that allow you to store multiple elements of the same type. Think of an array like a row of boxes, where each box can hold one item of a specific type.
-  The square brackets [] tell Java that numbers is an array.
- Arrays in Java are fixed in size, but we can modify their elements.

**code**
<details>

```java
public class ArrayDemo {
    public static void main(String[] args) {
        int[] numbers ={1,2,3,4,5};
        System.out.println("The elements of the array are:");
        for(int i=0;i<numbers.length;i++){
            System.out.println("Elements at index "+i+": "+numbers[i]);
        }

        //part2
        int sum = 0 ;
        for(int i: numbers){
            sum += i;
        }
        System.out.println("The sum of the elements is:"+sum);

        //part3
        int max = numbers[0];
        for(int i=1;i<numbers.length;i++){
            if(numbers[i]>max){
                max=numbers[i];
            }
            else{
                continue;
            }
        }
        System.out.println("The maximum value in the array is: "+max);

        //part4 
        numbers[2]=10;
        System.out.println("\nAfter modifying the third element:");
        for(int i : numbers){
            System.out.print(i+" ");
        }
        System.out.println();
    }
}

```

</details>

### ArrayList
- ArrayLists are part of the Java Collections Framework and provide a more flexible way to work with lists of objects.  
 Unlike arrays, `ArrayLists can grow or shrink in size dynamically`.
- Note the import statement at the top. This tells Java that we want to use the ArrayList class in our program.

        ArrayList<String> fruits = new ArrayList<>();

- This creates an empty ArrayList that can hold String objects. The <String> part is called a "generic" and specifies the type of elements the ArrayList will contain.

⁉️what if i want mixed int as well as strings?

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");
The add() method appends elements to the end of the list.    

- size() returns the number of elements in the ArrayList,  
  get(index) retrieves the element at the specified index.
- set(index, element) replaces the element at the specified index with a new element. The ArrayList size remains the same.



**code**
<details><summary>ArrayList</summary>

```java
import java.util.ArrayList;

public class ArrayListDemo {
    public static void main(String[] args) {
        // We'll add our code here
        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        System.out.println("Fruits in the list:");
        for(String i : fruits){ //enhanced loop
            System.out.println(i);
        }

        //part2
        System.out.print("\nNumber of fruits: "+fruits.size());
        System.out.print("\nThe second fruit is: "+fruits.get(1));

        //part3
        fruits.set(1,"Blueberry");
        System.out.println("\nAfter replacing the second fruit:"+fruits);

        /*
        Unlike arrays, ArrayLists allow us to insert elements at any position 
        using the add(index, element) method. 
        This is different from set() which we saw earlier. Let's see how add() works:       
        */
        fruits.add(1,"Blackberry");
        System.out.println("/nAfter inserting Blackberry at index 1:");
        System.out.println(fruits);

        /*
        Let's understand what happened:
        - add(1, "Blackberry") inserts "Blackberry" at index 1
        - The existing elements at index 1 and beyond (Blueberry, Cherry) are automatically shifted one position to the right
        - The ArrayList size increases by 1
        - This is different from set() which would replace the existing element without shifting or changing the size
        */

        fruits.add(1,"Blackberry");
        System.out.println(fruits);
        fruits.set(1,"Blackberry");
        System.out.println(fruits);

        //remove
        fruits.remove("Cherry");
        System.out.println("\nAfter removing Cherry:");
        System.out.println(fruits);
/*
This removes the first occurrence of "Cherry" from the ArrayList.  
When an element is removed, any subsequent elements are shifted to the left to fill the gap.
*/

        System.out.println("\nDoes the list contain Apple? "+fruits.contains("Apple"));
        System.out.println("\nDoes the list contain Cherry? "+fruits.contains("Cherry"));
        //The contains() method checks if the ArrayList contains a specific element and returns a boolean value.
    }
}

```
</details>

<details><summary>converrting_Arrays</summary>

```java

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class ConversionDemo {
    public static void main(String[] args) {
        // We'll add our code here
        String[] colorArray = { "Red", "Green", "Blue" };
        List<String> colorList = Arrays.asList(colorArray);

        System.out.println("Array converted to ArrayList:");
        System.out.println(colorList);

        // Arrays.asList() converts an array to a List. Note that this creates a
        // fixed-size list backed by the original array.

        colorList.set(1, "Yellow");

        System.out.println("\nAfter modifying the ArrayList:");
        System.out.println(colorList);
        System.out.println("Original array after ArrayList modification:");
        System.out.println(Arrays.toString(colorArray));

        // Arrays.toString() is a convenient method to print an array

        ArrayList<Integer> numberList = new ArrayList<>();
        numberList.add(1);
        numberList.add(2);
        numberList.add(3);

        Integer[] numberArray = numberList.toArray(new Integer[0]);

        System.out.println("\nArrayList converted to array:");
        System.out.println(Arrays.toString(numberArray));

        // We use the toArray() method of ArrayList to convert it to an array. We pass
        // new Integer[0] as an argument, which acts as a hint for the type and size of
        // the array to be created.

        numberArray[0] = 100;
        System.out.println("\nAfter modifying the array:");
        System.out.println("Array: " + Arrays.toString(numberArray));
        System.out.println("ArrayList: " + numberList);

        /*
         * his demonstration shows how arrays and ArrayLists can be converted into each
         * other. It's important to note the difference in behavior:
         * 
         * When you convert an array to a List using Arrays.asList(), the resulting List
         * is backed by the original array. This means changes to the List will be
         * reflected in the array, and vice versa. When you convert an ArrayList to an
         * array using toArray(), you create a new array that is independent of the
         * ArrayList. Changes to this new array will not affect the original ArrayList.
         * Understanding these conversions and their behaviors is crucial when working
         * with different collection types in Java, especially when interfacing with
         * APIs or libraries that might prefer one type over the other.
         */
    }
}

```



### Summary   
- In this lab, we've explored two fundamental data structures in Java:
Arrays and ArrayLists. Let's recap what we've learned:

#### Arrays:

- We created and initialized arrays using the syntax int[] numbers = {1, 2, 3,
4, 5}; We learned how to access array elements using index notation, like
numbers[0] We iterated through arrays using both traditional for loops and
enhanced for loops We performed calculations with array elements, like
finding the sum and maximum value We saw that arrays have a fixed size, but
we can modify their elements ArrayLists:

- We created ArrayLists using ArrayList<String> fruits = new ArrayList<>(); We
learned how to add elements with add(), remove elements with remove(), and
access elements with get() We used methods like size(), set(), and contains()
to work with ArrayLists We saw that ArrayLists can grow and shrink
dynamically, offering more flexibility than arrays Converting between Arrays
and ArrayLists:

- We converted arrays to ArrayLists using Arrays.asList() We converted
ArrayLists to arrays using the toArray() method We observed the different
behaviors when modifying converted collections Arrays and ArrayLists are
essential tools in Java programming. Arrays are great for working with a
fixed number of elements and can be more efficient in terms of memory usage.
ArrayLists, on the other hand, offer more flexibility and a rich set of
methods for manipulating the collection.

- As you continue your Java journey, you'll find yourself using both arrays and
ArrayLists frequently. The choice between them often depends on your specific
needs - if you know the exact number of elements you'll be working with, an
array might be preferable. If you need a dynamic collection that can grow or
shrink, or if you need the additional methods provided by ArrayLists, then an
ArrayList would be the better choice.

  
</details>
 
 