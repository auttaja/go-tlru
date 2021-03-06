# go-tlru
An implementation of the [Time Aware Least Recent Used (TLRU)](https://arxiv.org/pdf/1801.00390.pdf) caching type for Go.

To start with this library, simply create a new cache with `NewCache(MaxLength, MaxBytes int, Duration time.Duration)`. The first argument specifies the max number of items which can be in the cache, the second argument defines the maximum number of bytes the cache can be (0 means infinite), and the third argument defines how long arguments will last roughly before they are purged. From here, the cache has 2 functions:
- `Get(Key interface{}) (item interface{}, ok bool)`: Gets the item from the cache by the key interface which was given. The ok boolean defines if it was in the cache and therefore was successfully fetched.
- `Set(Key, Value interface{})`: Adds an item with the specified key/value to the cache.
