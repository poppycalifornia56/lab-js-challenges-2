1. Challenge 1:

- Answer: b
- Explanation: 
when declare foo = "abc" at the global scope, it creating a variable that can be accessed and modified anywhere. inside the function bar(), there's no local declaration of foo (no let, const, or var), so when assign foo = "xyz", it modifying the global foo variable.

when bar() executes:
1. it changes the global foo from "abc" to "xyz"
2. it logs the current value of foo, which is "xyz"

after bar() completes, the global foo remains "xyz". so when log foo again outside the function, it will also show "xyz"

2. Challenge 2:

- Answer: c
- Explanation: 
  here the function example() has a parameter also called a. this creates a new variable a within the function scope that shadows (hides) the global a.
  when call example(a), it passes the value of the global a (which is 1) to the function. inside the function, it assigns 10 to the parameter a, but this only affects the local copy, not the global a.

  so:
  1. inside the function, a becomes 10, and that's what the first console.log(a) will output
  2. but outside the function, a is still 1, so the second console.log(a) will output 1

3. Challenge 3:

- Answer: c
- Explanation:
  
when this code runs:
1. the function declaration for sayHi is hoisted
2. the call to sayHi() executes successfully
3. it logs "Hi there!" to the console

4. Challenge 4:

- Answer: c
- Explanation:
  the const keyword prevents reassigning the variable to a different value (like doing a = {} would be an error), but it doesn't prevent modifying the properties of the object that the variable references, when modify b.num = 90, I changing the property of the object that both a and b reference.

  so:
  1. a and b both point to the same object
  2. modify that object through the b reference
  3. when log a, we see the modified object

5. Bonus - Challenge 5:

- Answer: c
- Explanation:
  1. create rabbit1 as an object with name "Bob" and age 30
  2. call magicHat(rabbit1), passing rabbit1 by reference
  3. inside magicHat:
    - first, modify the passed object's age to 10 with obj.age = 10. this changes the original rabbit1 object to { name: "Bob", age: 10 }
    - then reassign the obj parameter to a completely new object: { name: "Ada", age: 20 }
    - this reassignment doesn't affect the original rabbit1 object, it only changes what the local obj variable points 
  4. the returned object is assigned to rabbit2
  5. when log both rabbits:
    - rabbit1 is the original object with the modified age: { name: "Bob", age: 10 }
    - rabbit2 is the new object that was created and returned: { name: "Ada", age: 20 }