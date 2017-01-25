# Bloom-Filters
[![Build Status](https://travis-ci.org/Callidon/bloom-filters.svg?branch=master)](https://travis-ci.org/Callidon/bloom-filters) [![Coverage Status](https://coveralls.io/repos/github/Callidon/bloom-filters/badge.svg?branch=master)](https://coveralls.io/github/Callidon/bloom-filters?branch=master)

**Keywords:** bloom, filter, bloom filter, probabilistic, datastructure

JS implementation of probabilistic data structures: Bloom Filter (and its derived), HyperLogLog, Count-Min Sketch, Top-K and MinHash

# Table of contents

* [Installation](#installation)
* [Data structures](#data-structures)
	* [Classic Bloom Filter](#classic-bloom-filter)
* [Tests](#tests)
* [Documentation](#documentation)
* [References](#references)
* [License](#license)

## Installation

```bash
  npm install bloom-filters
```

## Data structures

### Classic Bloom Filter

```javascript
const BloomFilter = require('bloom-filters').BloomFilter;

// create a Bloom Filter with size 15 and 2 hash functions
let filter = new BloomFilter(15, 2);
filter.add('alice');
filter.add('bob');

// create a Bloom Filter from an array with a 1% error rate
filter = BloomFilter.from([ 'alice', 'bob' ], 0.1);

// lookup for some data
console.log(filter.has('bob')); // output: true
console.log(filter.has('daniel')); // output: false

// print false positive rate (around 0.1)
console.log(filter.rate());
```

### Top-K

```javascript
...
```

## Tests

Running with Mocha + Chai
```bash
# run tests
npm test

# generate coverage with istanbul
npm run coverage
```

# Documentation
Generate JSDoc in directory `doc/`
```
npm run doc
```
## References

* [Classic Bloom Filter](http://crystal.uta.edu/~mcguigan/cse6350/papers/Bloom.pdf): Bloom, B. H. (1970). Space/time trade-offs in hash coding with allowable errors. Communications of the ACM, 13(7), 422-426.
* [Cuckoo Filter](https://www.cs.cmu.edu/~dga/papers/cuckoo-conext2014.pdf): Fan, B., Andersen, D. G., Kaminsky, M., & Mitzenmacher, M. D. (2014, December). Cuckoo filter: Practically better than bloom. In Proceedings of the 10th ACM International on Conference on emerging Networking Experiments and Technologies (pp. 75-88). ACM.

## License
[MIT License](https://github.com/Callidon/bloom-filters/blob/master/LICENSE)
