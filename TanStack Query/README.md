<p>
 <h1 style="color:red;" align="center">TanStack Query Introducation</h1>
</p>


## 1. Basic Typescript TanStack Query
 Installation

  ```sh
     npm i @tanstack/react-query
     yarn add @tanstack/react-query
     or
     npm i @tanstack/react-query-devtools
     yarn add @tanstack/react-query-devtools
  ```

 Quick Start


  ```js
     import {QueryClient,QueryClientProvider,} from '@tanstack/react-query'
     const queryClient = new QueryClient()

     function App() {
      return (
    // Provide the client to your App
     <QueryClientProvider client={queryClient}>
      <Todos />
     </QueryClientProvider>
     )}
  ```

  Query Functions


```js
     useQuery({ queryKey: ['todos'], queryFn: fetchAllTodos })
     useQuery({ queryKey: ['todos', todoId], queryFn: () => fetchTodoById(todoId) })
     useQuery({
        queryKey: ['todos', todoId],
        queryFn: async () => {
           const data = await fetchTodoById(todoId)
            return data
       },
    })
    useQuery({
       queryKey: ['todos', todoId],
       queryFn: ({ queryKey }) => fetchTodoById(queryKey[1]),
   })
```
```js
     //Simple data fetch for TanStack Query
     const { isPending, isError, error, data: users } = useQuery({
        queryKey: ['users'],
        queryFn: async () => {
            const res = await fetch('http://localhost:5000/user');
            return res.json();
        }
    })
      if (isPending) {
        return <span className="loading loading-spinner text-primary"></span>
    }

    if (isError) {
        return <p>{error.message}</p>
    }
    // how to use app.js
     {users.map(user => <tr key={user._id}><td>{user.email}</td>}
    
     
```

```js
     //advance two data loading for example
     const {isError, error, data: users,refetch } = useQuery({
        queryKey: ['user'],
        queryFn: async () => {
            const res1 = await fetch('http://localhost:5000/user');
            const res2 = await fetch('http://localhost:5000/service');
            const data1=await res1.json();
            const data1=await res2.json();
            return {data1,data2}
        }
    })
//Note:: data in use to array data1,data2  for example
```
```js
     //create your hooks project::useHooks
     const useOrdereview=()=>{
          const {isError, error, data: users,refetch } = useQuery({
        queryKey: ['user'],
        queryFn: async () => {
        const res2 = await fetch('http://localhost:5000/service');
        const data1=await res2.json();
        return data1
        }
    })
   return {isError, error, data: users,refetch}
    }
   export default useOrdereview;
```
