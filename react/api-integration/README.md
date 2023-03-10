# React API Integration

Connecting front-end applications to REST APIs, GraphQL endpoints, and external services.

## Integration Strategies

### 1. Traditional `useEffect` + `fetch`
*   Simple, requires writing manual state handlers for data, loading states, and error states.

### 2. TanStack Query (React Query)
The industry standard for fetching, caching, synchronizing, and updating server state.
*   **Automatic Caching:** Deduplicates identical requests, caches results locally, and updates stale data in the background.
*   **Built-in States:** Exposes `data`, `isLoading`, `error`, `isFetching` states directly out-of-the-box.

```jsx
import { useQuery } from '@tanstack/react-query';
import axios from 'axios';

const fetchUser = async (userId) => {
  const { data } = await axios.get(`/api/users/${userId}`);
  return data;
};

function UserProfile({ userId }) {
  const { data, isLoading, error } = useQuery({
    queryKey: ['user', userId],
    queryFn: () => fetchUser(userId)
  });

  if (isLoading) return <div>Loading...</div>;
  if (error) return <div>Error loading user data!</div>;

  return <h1>{data.name}</h1>;
}
```
