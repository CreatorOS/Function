# Function

There are several ways to return outputs from a function.

Public functions cannot accept certain data types as inputs or outputs

## Returning many values from a function

Unlike other languages, solidity supports returning multiple return values from a function.

Let's write a function that returns three values.

```
    function returnMany()
        public
        pure
        returns (
            uint,
            bool,
            uint
        )
    {
        return (1, true, 2);
    }
```

## Returning named values from a function

We can even name return values.

```
    function named()
        public
        pure
        returns (
            uint x,
            bool b,
            uint y
        )
    {
        return (1, true, 2);
    }
```

## Getting return values without return statement

- Return values can be assigned to their name.
- In this case the return statement can be omitted.

```
    function assigned()
        public
        pure
        returns (
            uint x,
            bool b,
            uint y
        )
    {
        x = 1;
        b = true;
        y = 2;
    }
```

## Destructuring return values

Use destructing assignment when calling another function that returns multiple values.

Code this function:

```
    function destructingAssigments()
        public
        pure
        returns (
            uint,
            bool,
            uint,
            uint,
            uint
        )
    {
        (uint i, bool b, uint j) = returnMany();

        // Values can be left out.
        (uint x, , uint y) = (4, 5, 6);

        return (i, b, j, x, y);
    }
```

Call the function above to test if destructing assignment worked or not.

## Limitations of functions

- We cannot use map for neither input nor output

- But we can use array for input like this:

```
    function arrayInput(uint[] memory _arr) public {}
```

- We can use array for output as well like this:

```
uint[] public arr;

function arrayOutput() public view returns (uint[] memory) {
    return arr;
}
```
