# About the project:

This project is a seat reserver application. The application needs two parameters: the number of seats we want to reserve and the number of already reserved seats. The application has a search algorythm which will recommend the best seat/seats according to their Tiers if there are multiple options the program will evaluate the best option based on the distance from the stage and the distance from the middle. It also has a graphical interface to make the results more visible.

# Installation:

    1. Copy the path of the index.html file and paste it into your browser
    2. Or just click the link: https://silly-rabanadas-35b078.netlify.app/

# Functionality

The application's functions are divided into 3 parts:
    1. GUI related functions
    2. Seat reservation related functions
    3. Seat visualization related functions

## GUI related functions

The GUI was made with HTML and CSS. It has basic design and responsivity.

## Seat reservation related functions

    1. It starts reserveRandomSeats which generates random numbers as many as the user wants but minimum 20% and maximum 100% of all the seats and set their reserved property to TRUE.
    2. After that the helper functions:
        - resetArray: cleanup function, clears random numbers' array
        - getSeat: returns a given seat's data
        - getMedian: returns the given row's median
        - getSeatDistanceFromMedian: evaluates the absolute distance of a seat from the median
    they help to avoid code repetition.
    3. Then comes compareOptions, it evaluates from the possible options which one is the most suitable, which one is:
        - the best based on tiers
        - the closest to the stage
        - the closest to the middle of the row
    4. At last findFreeSeats, which iterates over the database and finds suitable, not reserved seats or sequences, collects them into an array which is evaluated by compareOptions.

## Seat visualization related functions

    1. visualiseSeats: creates a schematic HTML layout of the seats in the auditorium and on the balcony
    2. visualiseReservedStatus: iterates over the HTML layout and gives the adequate className to the HTML element
    3. clearClassNames: cleanup function, removes inadequate classNames from HTML elements