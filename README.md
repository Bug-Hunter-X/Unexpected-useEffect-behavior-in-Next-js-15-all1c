# Next.js 15 useEffect Bug

This repository demonstrates a subtle bug related to the `useEffect` hook in Next.js 15.  The counter in `MyComponent` should increment every second, but it increments rapidly instead. This likely involves a misunderstanding or unexpected side effect of the `useEffect` cleanup function, specifically related to how intervals are managed within the component's lifecycle when re-rendering happens frequently in Next.js.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`
3. Run `npm run dev`
4. Observe the rapidly incrementing counter. 

## Solution

The solution involves using `useRef` to manage the interval ID, ensuring that only one interval is active at a time, preventing race conditions.  See the `bugSolution.js` file for the corrected code.