# debounce-hook-react

**debounce-hook-react is a custom React hook that provides debouncing functionality for handling input changes that should trigger a certain action after a short delay. It helps in preventing excessive function calls when dealing with fast-changing inputs like search bars or auto-suggestions.**

**Installation**

**You can install the debounce-hook-react package using npm or yarn:**

bash
```JSX
npm install debounce-hook-react # or yarn add debounce-hook-react

```

**Usage**

**Here's how you can use the useDebounce hook in your React components:**

```JSX

import React from 'react'; import useDebounce from 'debounce-hook-react'; 
function MyComponent() { 
    const [searchTerm, setSearchTerm] = React.useState(''); 
    const [debouncedSearchTerm] = useDebounce(searchTerm, 500); 
// Your logic for handling debouncedSearchTerm // ... 
    return ( 
        <input type="text" value={searchTerm} onChange={(e) => setSearchTerm(e.target.value)} placeholder="Search..." /> 
        ); 
    } 
export default MyComponent;

```

**In the above example, the useDebounce hook is used to debounce the searchTerm state variable. The debouncedSearchTerm will have a delay of 500 milliseconds before reflecting the changes made to searchTerm.**

**API**

**The useDebounce hook accepts two arguments:**

- value: The input value that needs to be debounced.
- delay: The time in milliseconds to delay the update of the debounced value.

**It returns an array with two elements:**

- debouncedValue: The debounced value that reflects the latest value after the specified delay.
- cancelDebounce: A function to cancel the debounce and reset the debounced value.

**Example**

```JSX

import React from 'react'; import useDebounce from 'debounce-hook-react'; 

function MyComponent() { 
    const [count, setCount] = React.useState(0); 
    const [debouncedCount, cancelDebounce] = useDebounce(count, 1000); 
    React.useEffect(() => { console.log('Debounced count:', debouncedCount); 

    return () => { 
        // Cancel the debounce when component unmounts cancelDebounce(); }; }, [debouncedCount]); 
        return ( 
            <div> 
                <button onClick={() => setCount((prev) => prev + 1)}>Increment</button> 
                <p>Count: {count}</p> <p>Debounced Count: {debouncedCount}</p> 
            </div> 
            ); 
        } 
export default MyComponent;

```
**License**

**This package is licensed under the MIT License - see the [LICENSE](https://chat.openai.com/LICENSE) file for details.**

**Thank you for using debounce-hook-react. If you have any issues, suggestions, or contributions, feel free to open an issue or a pull request on the [GitHub repository](https://github.com/yourusername/your-repo). Happy coding!**

