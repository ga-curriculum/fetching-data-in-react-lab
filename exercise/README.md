# ![Fetching Data in React Lab - Exercise](./assets/hero.png)

## Overview

![tktk Hunter - screenshots of app]()

In this lab, you will be retrieving data from the [Star Wars API (SWAPI)](https://swapi.dev/) and inserting it into the DOM. We will build an application that allows users to view a list of starships, and refine their results by searching for starships by name. In completing this lab, you will get some practice in fetching data from a third-party API in React.

Take a look at the component hierarchy diagram below for a sense of how this application will be structured:

![tktk Hunter]() 

In the list below, you'll find a brief description of the role of each component in our app:

- **App**: The root component that orchestrates the entire application.
- **StarshipSearch**: Allows users to submit a search form for the name of a starship.
- **StarshipList**: Displays a list of starships held in state.
- **StarshipCard**: A component used within `StarshipList` that displays information on a single starship.

## User stories

Here are the user stories for this lab:

- As a user, I should see a list of starship cards when the site loads. The list should also indicate the number of results that are being displayed currently.

- As a user, I should see the `name`, `starship_class`, `starship.manufacturer`, and `starship.model` rendered in each starship card.

- As a user, I should see a search bar above the list of starships. I should be able to enter in the name of a starship into the search bar, and submit my query.

- As a user, when I submit a search, the starship results being displayed should update based on my query.

## Lab exercise

Your primary goal is to implement the user stories listed above. To get started, you can follow the steps below:

1. Research the documentation of [**SWAPI**](https://swapi.dev/documentation) to find the endpoint for the `starships` resource. Figuring out documentation is a critical skill for a developer, so devote 10-15 mins just to looking through everything. You're not going to understand it all, but you should learn a bit in the process. There is also a very nice [home page](https://swapi.dev/) that allows you test out calls that you'd like to make. Try making some calls using this tool as well.

2. Create a `src/services/starshipService.js` service module and ensure that you make all API/fetch calls from this module. Use named exports to expose AJAX functionality as needed, e.g., `export { index }` or `export { search }` to obtain all starships.

3. Referencing the SWAPI documentation, create a `BASE_URL`.

4. Create a service function to retrieve a list of starships. In your service function, be sure to make use of your `BASE_URL` when making a `fetch()`.

5. Create each of the components listed below.

    - `src/components/StarshipSearch.jsx`
    - `src/components/StarshipList.jsx`
    - `src/components/StarshipCard.jsx`

6. After creating each component, import `StarshipSearch` and `StarshipList` at the top of `src/App.jsx`. In `src/components/StarshipList.jsx`, import the `StarshipCard` component. This will be used when mapping through `props.starships`.

7. In `src/App.jsx`, import `useState` from `react` and create a new `useState` variable called `starships`. Set its initial state to an empty array (`[]`).

8. In `src/App.jsx`, import the `useEffect` hook. Use this to call upon your service function when the page loads. Set the retrieved data to `starships` state. Focus on displaying the default starship results before implementing the search functionality.

> 🚨 Because data from the API is loaded asynchronously, there are times, such as if the user refreshes the page, that the data won’t be available to render. In this case, you may need to display a “Loading…” message instead.

## Level up

Once you have completed the lab, pick another resource from the ones listed on the left of the [documentation page](https://swapi.dev/documentation) (e.g. People, Species, Planets, etc...) and build a user interface implementing the same functionality for starships.