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



**code**
<details><summary>ArrayList</summary>

```java
```
</details>