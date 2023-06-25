# eloquent-javascript-resume

## Data structures :  Objects and arrays

### Arrays

    JavaScript provides a data type specifically for storing sequences of values. It is called an array and is written as a list of values between square brackets, separated by commas.

    ````
    let listOfNumbers = [2, 3, 5, 7, 11];
    console.log(listOfNumbers[2]);
    // → 5
    console.log(listOfNumbers[0]);
    // → 2
    console.log(listOfNumbers[2 - 1]);
    // → 3
    ````
    # Properties

    The two main ways to access properties in JavaScript are with a dot and with square brackets. Both value.x and value[x] access a property on value—but not necessarily the same property. The difference is in how x is interpreted. When using a dot, the word after the dot is the literal name of the property. When using square brackets, the expression between the brackets is evaluated to get the property name. Whereas value.x fetches the property of value named “x”, value[x] tries to evaluate the expression x and uses the result, converted to a string, as the property name.

    So if you know that the property you are interested in is called color, you say value.color. If you want to extract the property named by the value held in the binding i, you say value[i]. Property names are strings. They can be any string, but the dot notation works only with names that look like valid binding names. So if you want to access a property named 2 or John Doe, you must use square brackets: value[2] or value["John Doe"].

    The elements in an array are stored as the array’s properties, using numbers as property names. Because you can’t use the dot notation with numbers and usually want to use a binding that holds the index anyway, you have to use the bracket notation to get at them.

    The length property of an array tells us how many elements it has. This property name is a valid binding name, and we know its name in advance, so to find the length of an array, you typically write array.length because that’s easier to write than array["length"].

    #Methods

    ````
    let sequence = [1, 2, 3];
    sequence.push(4);
    sequence.push(5);
    console.log(sequence);
    // → [1, 2, 3, 4, 5]
    console.log(sequence.pop());
    // → 5
    console.log(sequence);
    // → [1, 2, 3, 4]
    ````

    The push method adds values to the end of an array, and the pop method does the opposite, removing the last value in the array and returning it.

### Objects

    Values of the type object are arbitrary collections of properties. One way to create an object is by using braces as an expression.

    Delete operator

    The delete operator is a unary operator that, when applied to an object property, will remove the named property from the object. This is not a common thing to do, but it is possible.

    In operator

    The binary in operator, when applied to a string and an object, tells you whether that object has a property with that name. The difference between setting a property to undefined and actually deleting it is that, in the first case, the object still has the property (it just doesn’t have a very interesting value), whereas in the second case the property is no longer present and in will return false.

    Object.keys

    Object.keys is a function where you give it an object, and it returns an array of strings—the object’s property names.
    
    ````
    console.log(Object.keys({x: 0, y: 0, z: 2}));
    // → ["x", "y", "z"]
    ````

    Objects.assign

    Object.assign function that copies all properties from one object into another.

    Arrays, then, are just a kind of object specialized for storing sequences of things. If you evaluate typeof [], it produces "object".

### Mutability

    Numbers, strings, and Booleans, are all immutable—it is impossible to change values of those types. 
    In the other hand, objects work differently. You can change their properties, causing a single object value to have different content at different times.

    With objects, there is a difference between having two references to the same object and having two different objects that contain the same properties.
    
    `````
    let object1 = {value: 10};
    let object2 = object1;
    let object3 = {value: 10};

    console.log(object1 == object2);
    // → true
    console.log(object1 == object3);
    // → false

    object1.value = 15;
    console.log(object2.value);
    // → 15
    console.log(object3.value);
    // → 10
    `````

    The object1 and object2 bindings grasp the same object, which is why changing object1 also changes the value of object2. They are said to have the same identity. The binding object3 points to a different object, which initially contains the same properties as object1 but lives a separate life.

    Bindings can also be changeable or constant, but this is separate from the way their values behave. Even though number values don’t change, you can use a let binding to keep track of a changing number by changing the value the binding points at. Similarly, though a const binding to an object can itself not be changed and will continue to point at the same object, the contents of that object might change.

    `````
    const score = {visitors: 0, home: 0};
    // This is okay
    score.visitors = 1;
    // This isn't allowed
    score = {visitors: 1, home: 1};
    `````




    


