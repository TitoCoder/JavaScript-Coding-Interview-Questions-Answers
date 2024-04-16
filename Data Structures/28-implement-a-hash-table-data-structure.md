# Write a function to implement a hash table data structure

## Problem Description

A hash table, also known as a hash map, is a data structure that allows for efficient storage and retrieval of key-value pairs. It works by using a hash function to convert a key into an index within an array, where the corresponding value is stored. This allows for constant-time (O(1)) access to the value associated with a given key, making hash tables highly efficient for many common use cases.

## Requirements

Implement a hash table data structure with the following functionality:

1. **Set(key, value)**: Adds a new key-value pair to the hash table, or updates the value of an existing key.
2. **Get(key)**: Retrieves the value associated with the given key, or returns `undefined` if the key is not found.
3. **Delete(key)**: Removes the key-value pair associated with the given key from the hash table.
4. **Hash(key)**: Implements a hash function that converts the given key into an index within the underlying array.

The hash table should be able to handle collisions (when two keys hash to the same index) using a suitable collision resolution technique, such as chaining or open addressing.

## JavaScript Code

Here's an implementation of a hash table in JavaScript:

```javascript
class HashTable {
  constructor(size = 10) {
    this.size = size;
    this.buckets = new Array(size).fill(null).map(() => []);
  }

  hash(key) {
    let hash = 0;
    for (let i = 0; i < key.length; i++) {
      hash = (hash + key.charCodeAt(i) * i) % this.size;
    }
    return hash;
  }

  set(key, value) {
    const index = this.hash(key);
    const bucket = this.buckets[index];
    const entry = bucket.find(([k]) => k === key);
    if (entry) {
      entry[1] = value;
    } else {
      bucket.push([key, value]);
    }
  }

  get(key) {
    const index = this.hash(key);
    const bucket = this.buckets[index];
    const entry = bucket.find(([k]) => k === key);
    return entry ? entry[1] : undefined;
  }

  delete(key) {
    const index = this.hash(key);
    const bucket = this.buckets[index];
    const entry = bucket.find(([k]) => k === key);
    if (entry) {
      bucket.splice(bucket.indexOf(entry), 1);
    }
  }
}

// Example usage:
const hashTable = new HashTable();
hashTable.set('apple', 1);
hashTable.set('banana', 2);
hashTable.set('cherry', 3);
console.log(hashTable.get('banana')); // Output: 2
hashTable.delete('banana');
console.log(hashTable.get('banana')); // Output: undefined
```

In this implementation, the hash table uses an array of "buckets" to handle collisions. The `hash` function converts the key into an index within the array, and the `set`, `get`, and `delete` methods handle adding, retrieving, and removing key-value pairs, respectively.

The hash function used in this example is a simple one that combines the character codes of the key with their positions in the string. You can experiment with different hash functions to find one that works well for your specific use case.