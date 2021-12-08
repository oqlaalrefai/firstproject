# Hashtables
Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value

### Terminology 
- hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose.
  -  it is used to determine the index of the array.
  - hash is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.

- bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. 
  - An index could potentially contain multiple key/value pairs if a collision occurs.

- collision is what happens when more than one key gets hashed to the same location of the hashtable.

### we use them for :
- Hold unique values
- Dictionary
- Library

### Creating a Hash :
* Add or multiply all the ASCII values together.
* Multiply it by a prime number such as 599.
* Use modulo to get the remainder of the result, when divided by the total size of the array.
* Insert into the array at that index.

### Colllision
If two keys ever ultimately resolved to the same index, then two calls to .Add(key, val) with different keys would overwrite each other.
Collisions are solved by changing the initial state of the buckets. Instead of starting them all as null we can initialize a LinkedList in each one! Now if two keys resolve to the same index in the array then their key/value pairs can be stored as a node in a linked list


### Hash maps do this to store values:
* accept a key
* calculate the hash of the key
* use modulus to convert the hash into an array index
* store the key with the value by appending both to the end of a linked list

### Hash maps do this to read value:
* accept a key
* calculate the hash of the key
* use modulus to convert the hash into an array index
* use the array index to access the short LinkedList representing a bucket
* search through the bucket looking for a node with a key/value pair that matches the key you were given

### Bucket Sizes
If a hash map has only a few buckets it will be densely full and have many collisions. If a hash map has more buckets it will be more sparsely populated, there will be less collisions, but there may be a lot of extra empty space.

- **load factor** tells us something about how full the hash table is.

### Internal Methods
1. Add() : When adding a new key/value pair to a hashtable
2. Find() : The Find takes in a key, gets the Hash, and goes to the index location specified.
3. Contains() : The Contains method will accept a key, and return a bool on if that key exists inside the hashtable. 
4. GetHash() : will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.
