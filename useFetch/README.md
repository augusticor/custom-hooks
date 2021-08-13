# useFetch

### Description

Hook for "fetching" data from an A.P.I. controling if the data takes too long to arrive and the component has been unmounted.

### Return state of the hook:

The hook returns an object { } of fetch result, until the data is retrieved:

```javascript
{ data: null, loading: true, error: null }
```

After that, if the request success:

```javascript
{ data: jsonData, loading: false, error: null }
```

But if there's an error:

```javascript
{ data: null, loading: false, error: 'Error message' }
```

### Parameters of the hook:

**originUrl**

The A.P.I. url for fetching the information, it's mandatory, example:

```
https://www.breakingbadapi.com/api/quotes/1
```

Which gets a quote from the [Breaking bad API](https://breakingbadapi.com/)

### Example

Example getting a random quote from the [Breaking bad API](https://breakingbadapi.com/)

```javascript
const { data, loading, error} = useFetch('https://www.breakingbadapi.com/api/quote/random');

// First state:
{ data: null, loading: true, error: null }

// Complete state for this A.P.I:
{
    data: [
        {
        "quote_id": 100,
        "quote": "FYI, old people adore me.",
        "author": "Jimmy McGill",
        "series": "Better Call Saul"
        }
    ],
    loading: false,
    error: null
}

// Error state:
{ data: null, loading: false, error: 'Error loading the info !!' }
```
