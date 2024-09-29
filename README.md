# Hospitality Domain Power BI Dashboard
## Project Overview
AtliQ Grands, a hotel chain is facing challenges due to increased competition and poor management decisions. Their market share and revenue in the luxury/business hotels category have been declining. To address this, the managing director wants to leverage “Business and Data Intelligence” to regain their competitive edge. However, they lack an in-house data analytics team to provide the necessary insights. To overcome their problems I was the data analyst who was provided with sample data and a mock-up dashboard to work on the following tasks:
 1. Create the metrics according to the metric list.
 2. Create a dashboard according to the mock-up provided by stakeholders.
 3. Create relevant insights that are not provided in the metric list/mock-up dashboard.

I worked on this project by following the Codebasics PowerBi Course, Link to the course is [here](https://codebasics.io/bootcamps/data-analytics-bootcamp-with-practical-job-assistance).

[Live Report Link](https://app.powerbi.com/view?r=eyJrIjoiMjFjMDg0M2EtYjE0YS00YWIxLTgwNDEtYjNlNjkzMTc4NGY4IiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)

Visit My Presentation Video on LinkedIn -> <a href="https://www.linkedin.com/posts/atharvasutar_datascience-powerbi-activity-7246149581787348993-kgyX?utm_source=share&utm_medium=member_desktop" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/posts/atharvasutar_datascience-powerbi-activity-7246149581787348993-kgyX?utm_source=share&utm_medium=member_desktop" height="30" width="40" /></a>

## Tech stacks
* PowerBi Desktop
* Excel
## PowerBI techniques Learnt
* What are all the questions that should be asked before starting the project
* Creating calculated columns
* Creating measures using the DAX language
* Data modeling
* Using Bookmarks to switch between two visuals
* Page navigation with buttons
* Using the divide function to prevent zero division errors
* Using KPI indicators
* Conditional formatting of the values in visuals using icons or background color
* Data validation techniques
* PowerBi services
* Publishing reports to PowerBi services
* And more 😅
## Business related terms
* Revenue
* Occupancy
* Avg. Rating
* Cancellation %
* Realization %
* Revenue Per Available Room
* Average Daily Rate
* Daily Sellable Room Nights
* Daily Utilized Room Nights
* Daily Booked Room Nights
## Company’s Background
AltiQ Grands is a hotel chain based in India that has grown vastly recently. It is a company that operates in the following categories:
* Luxury
* Business
The company is facing challenges due to increased competition and poor management decisions. Their market share and revenue in the luxury/business hotels category have been declining. To address this, the managing director wants to leverage “Business and Data Intelligence” to regain their competitive edge. However, they lack an in-house data analytics team to provide the necessary insights.

Project kick-off session, where you should get clear of what and why this project is and all other questions you have with regards to the project

### Questions to ask before starting with the dashboard
* What is the objective of building this PowerBi dashboard?
* In what terms the success of this project will be measured?
* What will be the deadline for the project?
* Do the stakeholders expect a pre-view before the actual release?
* What are all the hopes stakeholders have out of this project?
* What are all the fears the stakeholders have in terms of building this dashboard?
* Who will be using this dashboard and for what purpose?
* What are all expectations the stakeholders have, by the completion of this project?
* What can go wrong while building this project?
* What are all the resources/ data needed to build this dashboard?
* Is there any input from stakeholders in terms of design and views of the dashboard?
After the project kick-off meetings, the data engineering team has given the data as per the request of the data analytics team, let’s explore them.

### Dataset Understanding
Understanding what data is available will be more helpful while doing analysis. before jumping on to the analysis get a good understanding of what is the available data.

Dimension table: It will have static data like details of customers and products

Fact table: It will have the data about the transactions

Column Description for dim_date:
1. date: This column represents the dates present in May, June, and July.
2. mmm yy: This column represents the date in the format of mmm yy (monthname year).
3. week no: This column represents the unique week number for that particular date.
4. day_type: This column represents whether the given day is a Weekend or Weekday.
Column Description for dim_hotels:
1. property_id: This column represents the Unique ID for each of the hotels.
2. property_name: This column represents the name of each hotel.
3. category: This column determines which class[Luxury, Business] a particular hotel/property belongs to. 
4. city: This column represents where the particular hotel/property resides.
Column Description for dim_rooms:
1. room_id: This column represents the type of room[RT1, RT2, RT3, RT4] in a hotel.
2. room_class: This column represents to which class[Standard, Elite, Premium, Presidential] particular room type belongs.
Column Description for fact_aggregated_bookings:
1. property_id: This column represents the Unique ID for each of the hotels.
2. check_in_date: This column represents all the check_in_dates of the customers.
3. room_category: This column represents the type of room[RT1, RT2, RT3, RT4] in a hotel.
4. successful_bookings: This column represents all the successful room bookings that happen for a particular room type in that hotel on that particular date.
5. capacity: This column represents the maximum count of rooms available for a particular room type in that hotel on that particular date.
Column Description for fact_bookings:
1. booking_id: This column represents the Unique Booking ID for each customer when they booked their rooms.
2. property_id: This column represents the Unique ID for each of the hotels
3. booking_date: This column represents the date on which the customer booked their rooms.
4. check_in_date: This column represents the date on which the customer check-in(entered) at the hotel.
5. check_out_date: This column represents the date on which the customer check-out(left) of the hotel.
6. no_guests: This column represents the number of guests who stayed in a particular room in that hotel.
7. room_category: This column represents the type of room[RT1, RT2, RT3, RT4] in a hotel.
8. booking_platform: This column represents in which way the customer booked his room.
9. ratings_given: This column represents the ratings given by the customer for hotel services.
10. booking_status: This column represents whether the customer canceled his booking[Cancelled], successfully stayed in the hotel[Checked Out], or booked his room but not stayed in the hotel[No show].
11. revenue_generated: This column represents the amount of money generated by the hotel from a particular customer.
12. revenue_realized: This column represents the final amount of money that goes to the hotel based on booking status. If the booking status is canceled, then 40% of the revenue generated is deducted and the remaining is refunded to the customer. If the booking status is Checked Out/No Show, then the full revenue generated will go to hotels.

## Importing Data into PowerBi
* As the data is in CSV files, we need to simply import the folder in Power BI and manipulate it in Power Query.
## Data Model
* Data modeling plays a vital role and is considered as the basement of the report. All the visuals will be built upon the data model.
* Poor data modeling affects the overall performance of the report.
* Following Good practices of data modeling is a must.
* In this project, we have followed the Snowflake data modeling schema.
![Database Model](https://github.com/user-attachments/assets/fa20d6bd-ed76-4e7a-9d85-ce6faa56da04)


Dashboard designing
Based on the mock-ups received as requirements, I have designed the visuals and created measures.

Page Navigation
Page Navigation, is a bookmark that shows buttons to land on the desired view. The buttons are as follows:

* Overall Analysis
* Monthly Analysis

## Page Navigation
![Page Navigation](https://github.com/user-attachments/assets/fb2fbc30-617b-4408-9a03-1f45ee9cebfb)

## Overall Analysis View
![Overall Analysis View](https://github.com/user-attachments/assets/82bfbde4-f583-4f8c-a83b-e72efbd4fc2d)

## Monthly Analysis View
![Monthly Analysis View](https://github.com/user-attachments/assets/871d9e5e-201e-4d18-95cf-2f9869d60bd4)

## Project Outcome
1. Over 42% of the hotel rooms are currently empty. 
2. The average customer rating is a disappointing 3.6 out of 5. 
3. An alarming 25% of customers are canceling their bookings. 
4. Most of the revenue is generated from a single city, Mumbai.

## My Suggestions
1. Implement targeted marketing campaigns to reach potential guests through social media, email marketing, and online advertising.
2. Provide exceptional service to encourage repeat business and positive word-of-mouth referrals.
3. Analyze competitor’s pricing and adjust rates to offer better value without compromising the revenue.
4. Create attractive packages for holidays, special events, or off-peak times to entice bookings.
5. Invest in property upgrades to enhance customer experience.
6. Implement flexible booking and cancellation policies to make it easier for guests to choose your hotel.
