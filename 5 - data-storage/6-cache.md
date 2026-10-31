# Cache

Always be caching.

Reduce latency, improve user experience, decrease system load, and lower cost.

# There are so many different types of caches on every layers.

On browsers, we have local storage, HTTP cache. The types of data we catch on browser, including user preferences, responses, HTML, CSS, and JavaScript.

On the API service layer, we catch in-memory, disk cache, and the types of data we catch is a computed result in the API response.

On the database layer, we have query catch, buffer pool, and the types of data that we catch, including frequently accessed read data, indexes, and query results.

On CDN level, likes Fastly, Akamai, Open Connect.

And types of data we catch is the static assets.

## Cache aside, (lazy loading)

### READs

1. cache miss
2. read from database
3. update the cache

### WRITEs

1. write to the DB
2. write to the cache

## Write Through Cache

1. write to the cache
2. then cache Write to the DB

the cache in between

## Read Through Cache

1. Read from the cache
2. On miss, Read from database.
3. Write to cache.

## WRITE BEHIND

1. Write to cache
2. Immediately return.
3. Asynchronously Write to db.

Well, this concept is very similar to optimistic update on the UI on the front end. For 99.9% of the time, the grant is going to go through, and we're going to serve the user successfully with the transaction. But there is a slightly smaller and tiny chance that the user might see the still UI or something like that. That is a trade-off that we want to make.
