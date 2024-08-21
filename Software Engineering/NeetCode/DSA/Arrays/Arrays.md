An array is a linear data structure of fixed length in which all elements are stored contiguously. 
They allow for efficient read / write operations through the use of indexing.

| Index | 0 | 1 | 2 |
| ---- | ---- | ---- | ---- |
| **Values** | 1 | 3 | 5 |

## RAM - *Random Access Memory*

RAM refers to a contiguous block of data that stores both values and the addresses used to access to those values. The addresses of array data are stored contiguously in memory. Each address is incremented in accordance to the type of data stored in the array. E.g an int occupies 4 bytes so each address would be 4 bytes . A character consumes 1 byte and so each address allocated into the RAM would be 1 byte apart.

### Int Array
| Value | 1 | 3 | 5 |
| ---- | ---- | ---- | ---- |
| **Address** | $0 | $4 | $8 |
### Character Array
| Value | 'a' | 'b' | 'c' |
| ---- | ---- | ---- | ---- |
| **Address** | $0 | $1 | $2 |

How are arrays stored in `RAM`?

`RAM` data is stored in `bytes`
`1 byte` = `8 bits`

_1_ _0_ _0_ _1_     _1 0_ _0_ _1_

A `bit` is a position that can store a digit. They can take values ranging from `0` to `1`

## Array  Properties

Arrays are of a fixed length, meaning they the amount of data they hold is limited
. Once the array reaches maximum capacity, a larger array must be created to store any additional array elements.

## Array Operations

Array values are accessed using their indexes. Every array index maps to a location in memory. The available indexes for a given array are
`0 - length of array - 1`

Reading - O( 1 )

Writing - O( 1 )

Insert - O( N ) Inserting an element is efficient at the end of the array because a vacant position is already available to hold it's value. Anywhere else would result in ( array length - 1 ) - i shifts to the right.

Delete -  O( N ) - Deleting an array element results in ( array.length - 1 ) - i shifts to the left. Deleting array elements is most optimal from the end of the array due to the need for fewer shifts.


## Dynamic Arrays

