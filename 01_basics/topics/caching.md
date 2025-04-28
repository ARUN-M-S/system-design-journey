## 1. What is Caching?

Caching is the process of storing copies of data in a temporary storage (cache) so that future requests can be served faster.

Goal: Reduce database load, improve application performance.

## 2. Why Use Caching?

To reduce latency (faster response time).

To reduce load on backend/database.

To handle high traffic efficiently.

To improve scalability of the system.

## 3. Where to Use Caching?

Database queries (slow queries)

API responses (e.g., product details)

Web pages (static content)

Authentication tokens

## 4. Cache Data Structures

In-memory Key-Value stores (e.g., Redis, Memcached)

Local server memory (e.g., process-level cache)

## 5. Cache Eviction Policies

When the cache memory is full, we must decide which item to remove.

| Policy | Full Form               | Description                                         |
|:------:|:------------------------|:----------------------------------------------------|
| **LRU** | Least Recently Used      | Remove the item which was least recently accessed. |
| **LFU** | Least Frequently Used    | Remove the item which was accessed the least number of times. |
| **FIFO**| First In First Out       | Remove the oldest added item first.                |


Quick Example

LRU: If you haven't used "item1" for a long time, it gets removed first.

LFU: If "item2" was accessed only 1 time but "item3" accessed 5 times, "item2" will be evicted first.

FIFO: Regardless of usage, the item that entered first will be removed first.

## 6. How Caching Works Internally

Think of a simple JavaScript object:

{
  'iphone15': 'url1',
  'samsungS22': 'url2',
}

For fast lookup: Use HashMap.

For eviction tracking (like LRU): Use Doubly Linked List + HashMap together.

How?

HashMap helps you find a node in O(1).

Doubly Linked List helps you maintain recent order in O(1).

Example in LRU

Every time a key is accessed:

Move that key/node to the front (head) of the linked list.

When cache is full:

Remove the tail node (least recently used).

Thus, all operations (get, put, evict) happen in O(1) time!

## 7. Cache Consistency

Strategy

Description

Write Through

Update cache and DB together during write.

Write Around

Write directly to DB, cache updated only on read.

Write Back (Write Behind)

Write to cache first, periodically sync to DB.

Note: Write policies help ensure that cache and database do not get out of sync.

## 8. Popular Cache Systems

Redis (most popular)

Memcached

Local Memory (in-app cache)

## 9. Interview Points

Always explain: HashMap + Doubly Linked List combo.

LRU is most commonly asked.

Cache invalidation is a hard problem ("what to cache", "how long", "when to delete?").

Eviction policies are critical when memory is limited.

System Design round: Mention caching to reduce database hits!

## 10. Real-world Example

Amazon product page: Cache product details.

Twitter timeline: Cache latest tweets.

Netflix recommendations: Cache popular shows for your region.

## 11. Summary

Cache improves performance by storing frequent data closer.

Eviction policies handle full cache smartly.

Correct architecture (hashmap + linked list) gives O(1) performance.

Learn cache with system design mind: when, where, why.

End of Caching Notes

Next Steps: Practice small cache codes like LRU, LFU, FIFO for better hands-on understanding!
