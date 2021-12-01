# Data Visualisation with Tableau

## About
The hotel_bookings_0421.csv data set contains hotel reservations information for Metropolis Grand Hotel and Island Grand Resort, and includes information such as when the booking was made, length of stay, the number of adults, children, and/or babies, and the number of available parking spaces, among other things. The metadata of the hotel_bookings_0421.csv dataset is provided in the accompanying metadata.txt file.
 <br>
 
 ## Explotary questions
 
Customer Analysis (customer behaviors and profile)
1.	What are the preferred visiting months for customers?
2.	What is the most famous meal package that customer order?
3.	Which country of customers visited the most?
4.	What is the most famous booking channel for customers? (Distribution channels)
5.	What are the percentages of new customers and repeated customers?
6.	What is the preferred room type for customers?
7.	What is the preferred deposit type for customers?
8.	What is the percentage of new customers and returned customers (repeated)?

Booking Cancellation (finding the reasons for cancellation of bookings)
1.	How many bookings are cancelled by the customer?
2.	Which distribution channel has the most customers cancelling the booking?
3.	What type of customer has the most cancellation of the booking?
4.	How is the average day in waiting list related to the cancellation of the booking?

Profitability (areas that the company can pay attention to increase the profit)
1.	How is the length of staying? night related to the customer Average Daily Rate (ADR)? 
2.	How is the meal type that the customer chose related to the customer ADR?
3.	How is the customer type related to the customer ADR?

## Data Preparation
-	State of data
The initial state of data is not cleaned yet, as some of the attributes such as is_canceled and is_repeated_guest is represented in 0 and 1, which might cause confusion to Tableau to interpret it as measures. Thus, a substantial data cleanup is needed in order to make data visualization easier in Tableau.

-	Data cleansing
1.	Make a new calculated field “IsCanceled” with the following command: 
[Is Canceled] = 1, so as to convert the 0s and 1s in “Is Canceled” to Boolean values.
2.	Make a new calculated field “IsRepeatedGuest” with the following command:  
IF [Is Repeated Guest] = 1 THEN "Old Customer"
ELSE "New Customer"
END
3.	Make a new calculated field “Arrival Date” with the following command:
MAKEDATE([Arrival Date Year],MONTH(DATEPARSE("MMM", [Arrival Date Month])), [Arrival Date Day Of Month])
4.	Make a new calculated field “Total Stay” with the following command:
[Stays In Week Nights] + [Stays In Weekend Nights]

## Dash board <br>

![image](https://user-images.githubusercontent.com/73086331/144263614-14838162-f102-49bb-8c9e-78efdcfe6e50.png)


![image](https://user-images.githubusercontent.com/73086331/144263985-f5757940-8071-409b-ad07-4fb699378bad.png)


![image](https://user-images.githubusercontent.com/73086331/144263816-6a0a3790-41b0-4cc3-89fc-9511277db29f.png)







 
