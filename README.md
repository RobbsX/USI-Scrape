This repo scrapes data from all sport courses of the [USI website](usi.at). 

Python, Selenium, BeautifulSoup4, matplotlib

## Goal
For creating an own USI course, it is important to know the structure of other courses. With that, I wanted to find out at what time, at what price, and with how many capacity I should calculate, and if a second course makes sense when usage of the room is low. This was the perfect opportunity to web scrape! 


## Result
*The scrape allowed me to make an informed decision for the course parameters. My expectations were surpassed! In the first run, we were almost booked out.*

_Details_

Time: Our new sport course was set from 18:15 to 19:45 - which payed of as there were many bookings! A trail course from 11:30 to 13:00 did not take place as there were too few bookings, as expected. In general, the worst times to make a course are: 6:43 to 7:42, 11:30 to 12:24, and 13:24 to 14:21. Notably, courses from 15:18 to 21:00 are well booked, especially from 19:06 to 20:03.

![image](https://github.com/RobbsX/USI-Scrape/assets/79597633/f77978f9-ce5c-49e7-b33e-7de3e7adefba)

Visualisation of Free Spots over Time


Price I: EUR 79 was taken because it had a good balance between price per lesson and effort for this kind of course, and at the location. In comaprison to toher courses, this course is just below the upper quantile for Price I, and very low for Price II or III. 

![image](https://github.com/RobbsX/USI-Scrape/assets/79597633/39c745e2-1605-484d-bb8c-09013088269c)

Average price distribution of courses

Capacity and expected bookings: The limit was set to 30 people, with an expected booking number of 28. 


## Further Steps
I would have liked to get the number of lessons per course to make the pricing even more precise. However, this data is, if available, not sturctured throughout the website. 


## Approach
This is a screenshot of the list of the sport courses, as well as an example course, to visualise the scraping source.

<img width="1168" alt="USI_Course_List" src="https://github.com/RobbsX/USI-Scrape/assets/79597633/20574bc7-e2f9-47ef-a45e-f999601c8565">
Screenshot of list of all sport courses. 

<img width="1165" alt="USI_Course_Exp" src="https://github.com/RobbsX/USI-Scrape/assets/79597633/c89484f9-6e9c-4583-a1eb-e2f165a6e69e">
Screenshot of one example sport course. 

The data scraped is: 
Kurs Name, Kurs Nr: Course name and number. 
Tag: Day.
Zeit Von, Zeit Bis: Time from X to Y. 
Ort: Location of course hall. 
Limit: Maximum capacity of the course. 
Freie Plätze: Free sport left.
Preis I, Preis II, Preis III: Price per age group and graduates; Students up to 25, Students from 25, Graduates. 
TryUSI: Boolean Variable whether the course is on trail with one-third of the original price. 
