# A Booking website using React hooks

This is a booking website for a company's internal booking management. It is a practice project for the book _React Hooks in Action_ by JOHN LARSEN.

## Table of contents

- [A Booking website using React hooks](#a-booking-website-using-react-hooks)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [Requirements](#requirements)
    - [Screenshot](#screenshot)
    - [Links](#links)
  - [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Continued development](#continued-development)
    - [Useful resources](#useful-resources)
  - [Author](#author)
  - [Acknowledgments](#acknowledgments)

## Overview

### Requirements

The entire application is divided into four categrouies of components: Bookables, Bookings, Users and UI

### Screenshot

![screenshot1](./screenshots/Booking_management_snapshot.png)
![screenshot2](./screenshots/Booking_management_snapshot2.png)
![screenshot3](./screenshots/Booking_management_snapshot3.png)
![screenshot4](./screenshots/Booking_management_snapshot4.png)

### Links

- Live Site: [Booking-site](https://haolzz.github.io/Booking/)

## My process

### Built with

- CSS custom properties
- CSS Flexbox and Grid for layout
- React hooks for React component state management
-

### What I learned

1. Functionality that could be shared means we can extarct it into a custom hook. In this example code below, the data fetching function is encapsulated within a custom hook called `useFetch`.

   ```js
   import { useState, useEffect } from 'react';
   import { getData } from './api';
   export default function useFetch(url) {
     const [data, setData] = useState();
     const [error, setError] = useState(null);
     const [status, setStatus] = useState('idle');
     useEffect(() => {
       let doUpdate = true;

       setStatus('loading');
       setData(undefined);
       setError(null);

       getData(url)
         .then((data) => {
           if (doUpdate) {
             setData(data);
             setStatus('success');
           }
         })
         .catch((error) => {
           if (doUpdate) {
             setStatus('error');
             setError(error);
           }
         });

       return () => (doUpdate = false);
     }, [url]);
     return { data, status, error };
   }
   ```

### Continued development

- Rewrite with TypeScript
- Beautify website using Material-UI

### Useful resources

## Author

- GitHub - [Haoliang Zhang](https://github.com/HaoLZz)
- LinkedIn - [Haoliang Zhang](https://www.linkedin.com/in/haoliangzhangengineer/)

## Acknowledgments

```

```
