# Small Cache

🎈 The simplest, easiest, and most minimalist way 😃 to cache your requests on your frontend (JS/TS, with React.js, Next.js, Vue.js, Angular, and all others)

It's as easy as this:
```ts
const creatorsListData = await getFromCache(
  'creators', // cache key
  async () => await creatorsService.get() // the fetch data function
)
```

Or as simple as:
```ts
const product = await getFromCache<Product>(
  'product-123', // cache key
  async () => { // the fetch data function
    const { data } = await axios.get<Product>('https://example.com/products/123')
    return data;
  }
)
```

You can also control the cache TTL (Time to Live) or disable caching using a third parameter, the options:
```ts
const creatorsListData = await getFromCache(
  'creators', // cache key
  async () => await creatorsService.get() // the fetch data function,
  { // options parameter
    TTL_InSeconds: 60, // cache TTL (time to expire in seconds)
    enabled: true // enable or disable the caching
  }
)
```

---

And yes, that's all! <br />
Life can be simple sometimes ✨
