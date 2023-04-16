### Weather app using Reactjs and OpenWeatherMap API ###

![preview](https://user-images.githubusercontent.com/129972263/232322247-f16a5d70-a52e-4ecc-a3d4-d714c43a3a2e.png)

Preview

### Project details ###
This app uses ReactJS for the gui and OpenWeatherMap's API To get weather data. This app mainly consists of 3 components.

CityForm.js component is used to search for different city data. It takes 2 props, cityChange (Which is a function in app.js that changes the url to get a different city's weather data), and spinner (Which makes the spinner visible depending on if it is true or not). when the submit button is clicked, it runs the cityChange function with the city as a parameter.

Today.js displays today's weather from the json data given by the API. It takes Data as a prop. the entirety of the json data is sent into the component through this prop.

Slides.js displays a 5 day weather forecast. it takes Data as a prop. only the list json is sent into the prop. From there it runs a for loop which checks the dt_txt field, which shows both date and tim of the data to check if the date is different. the first 10 letters are the date, so it slices upto the 10th letter to check only date. it checks 2 variables d1 and d2. d1 is dt_txt of the previous json and d2 is dt_txt of the current json. if they are different, it pushes the data into an array called listdata. since the API Returns data in 3 hour intervals (first it returns the weather data at 12Am, then 3am, then 6am, etc), it actually pushes the 4th data from the current date to get the data for 12pm. the map function is then used on listdata to create the actual forecasts.

axios library is used in app.js to get weather data from the api.


### Project Setup ###

Step 1: run npm install. this will install all the project dependencies for you.

Step 2: This app uses OpenWeatherMap's API To get weather data, so if you dont have an account on there, you will first have to sign up for the free plan at https://openweathermap.org/price

Step 3: in the .env file, replace REACT_APP_API_KEY with your api key. You do not have to change REACT_APP_API_URL.

Step 4: you are good to go, Open command prompt and run npm start to start the project
