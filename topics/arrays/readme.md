# Array Operations

One key thing to keep in mind every time we work with React is the concept of immutability. To re-render things, we need to pass it on a new data, and we usually do this by copying the data, modifying it, and then return it. Luckily javascript gut us covered by providing some methods to work with arrays that allow us to do our operations and return a new array.

 - Map
 - Filter
 - Spread operator


## Map
Map is a method that allows us to iterate over an array and return a new array with the result of the callback function. This is probably the most used method when working with arrays on React because it allows to iterate and render a series of components from the data in the original Array.
Let says we have an array of persons, and we want to render a list of persons. We can do this by using the map method.

    const people = ["Jose Raul", "Alexander", "Mikhail","Bobby", "Garry"]

    //We can render this list:
    <ul>
     {people.map(name => <li key={name}>{name}</li>)}
    </ul>


In the example above, we go through the whole array of data and convert it into a list of components.



## Filter

The filter method will return an array with the items of the original array that pass a test specified in a callback function; this is very useful to remove some items from the original array. Take, for example.

    const champions = [ 
        {
            name : "Boris Spassky",
            country : "USSR",
        },
        {
            name : "Robert James Fischer",
            country : "USA",
        },
        {
            name : "Jose Raul Capablanca",
            country : "CUBA"
        },
        {
            name : "Anatoly Karpov",
            country : "USSR",
        },
    ]

    // This creates an array without Boris Spassky and Anatoly Karpov
    const notUssr = champions.filter(champion => champion.country !== "USSR");

    // This creates an array only with the USSR champions
    const onlyUssr = champions.filter(champion => champion.country === "USSR");


## Spread

The spread operator (...) allows us to "expand" an array. This is very useful when creating a new array and adding it to a new Item; remember that it is vital to create a modified copy of the data and not mutate it directly; hence a push won't do the job.

    const players = [
        {
            name : "Boris Spassky",
            country : "USSR",
        }
    ]

    const fischer = {
        name : "Robert James Fischer",
        country : "USSR"
    }

    // This will add the object fischer to the array matchOfTheCentury
    const matchOfTheCentury = [...playes, fischer];
    
    // if we print the array matchOfTheCentury we will get
    [
        {
            name : "Boris Spassky",
            country : "USSR",
        },
        {
        name : "Robert James Fischer",
        country : "USSR"
        }
    ]

    And the two arrays will be different, players remain untouched, and we got ourserlves a new array by spreading the player's array and adding at the end a new item.

