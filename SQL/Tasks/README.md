# 1. Insurance System
## Exercises:
- a) Display all data about issued vehicle insurance policies (insurance type name = "VEHICLE INSURANCE") in the current month sorted by premium class.
- b) Delete all policies for which there was no payment after three months from the policy issue date.
- c) Create a view that displays by years, and within them by months, the total number of issued policies, total value of policies, for all types of property and life insurance (these are insurance types with names "PROPERTY INSURANCE", "LIFE INSURANCE") from 2000 onwards.
- d) Create a view "DISPUTEDCLAIMS" that displays POLICY_NUMBER, POLICY_DATE, TOTAL_LIABILITY, TOTAL_PAID, NUMBER_OF_APPROVED

# 2. Airport System
## Exercises
Given relational schema:
-  AIRPORT(AEROID, NAME, COUNTRY, CITY)
-  ROUTE(ROUTEID, DEPARTURE_AERO, DESTINATION_AERO)
-  FLIGHT(ROUTEID, DATE_TIME, PLANEID)
-  AIRCRAFT(PLANEID, DESIGNATION, AIRCRAFT_TYPE, NUM_SEATS)
-  RESERVATION(ROUTEID, DATE_TIME, SEQ_NUM, STATUS)

Write SQL:1999 commands that:
- a) Postpone all flights to Zurich on November 15, 2003 (update the STATUS attribute to 'Postponed').
- b) Display all direct flights from GREAT BRITAIN to GERMANY: date, time, route number, departure airport name, destination airport name sorted by departure date and time for all flights in the second quarter of the current year.
- c) Create a REALIZATION view that displays total realization for all routes in the current year. Display RouteNumber, NumberOfCompletedFlights, TotalNumberOfPassengers, TotalCapacities, AverageFlightOccupancy.

# 3. Project Management System
## Exercises
Given relational schema:
- PROJECT(PROJ_CODE, PROJECT_NAME, BUDGET, PROJECT_LEADER)
- ENGAGEMENT(WORKER_CODE, PROJ_CODE)
- WORKER(WORKER_CODE, WORKER_NAME, BIRTH_DATE, HIRE_DATE, SALARY, COMPANY_CODE, IS_MANAGER)
- COMPANY(COMPANY_CODE, NAME, CITY)

Write SQL:1999 commands that:
- a) Display all data about workers who completed 10 years of service in the current year and are engaged on at least 2 projects. OR
- b) Display all data about workers who have a salary greater than 30,000 dinars and are engaged on at least one project.
- c) Create a MANAGER view (CompanyName, WorkerName, WorkerCode, HireDate) that displays for all companies the names of managers who are not engaged on any project.
- d) Display age structure of workers by cities where they work (number of workers under 20 years, number of workers between 20 and 45 years, and number of workers over 45 years).

# 4. University System
## Exercises
Given relational schema:
- UNIVERSITY(UniversityCode, UniversityName)
- FACULTY(FacultyCode, FacultyName, UniversityCode)
- PROFESSOR(SSN, Name, Surname, HireDate, HomeFaculty)
- ENGAGEMENT(SSN, FacultyCode)
- PAYMENT(SSN, FacultyCode, PaymentDate, Amount)

Write SQL:1999 commands that:
- a) Display Surname, Name, YearsOfService, FacultyName for professors employed at a university with the name "Belgrade" in the last 10 years. Sort the result in descending order of years of service and ascending surname.
- b) Display for all universities the faculties that have the number of employed professors between 50 and 100, sorted in descending order within universities.
- c) Create a FEES view (Surname, Name, NumberOfFaculties, Month, TotalMonthlyPayment) that displays monthly payments to professors in the previous year who are engaged outside their home faculty. The NumberOfFaculties column shows the number of different faculties that paid fees to the professor in the given month.

# 5. Student Admission System
## Exercises
Given relational schema:
- PLACE(PlaceCode, PlaceName)
- SCHOOL(SchoolCode, SchoolName, SchoolType, PlaceCode)
- CANDIDATE(SSN, Surname, ParentName, Name, BirthDate, OverallSuccess, CompletedSchool, ApplicationDate, ApplicationNumber)
- CERTIFICATE(SSN, Year, Average, SchoolCode)
- GRADE(SSN, Year, Seq, SubjectName, Grade)

SchoolType in ('Agricultural', 'Technical', 'Gymnasium', 'other') Grade in (2,3,4,5)

Write SQL:1999 commands that:
- a) Display surname, name, school name, overall success and application number of all candidates who completed a technical school and applied on June 25, 2003. Sort results in ascending order of surname.
- b) Create a GeneralSuccess view (Success, NumberOfCandidates, AverageSuccess) that displays achieved success of candidates (excellent, very good, good, sufficient), number of candidates, average success of those candidates. Consider only certificates from the fourth year (final year).
- c) Create a SuccessByPlaces view (PlaceName, Success, NumberOfCandidates) that displays for each place the number of candidates for the specified school successes (excellent, very good, good, sufficient).

# 6. Football League System
## Exercises
Given relational schema:
- FOOTBALL_TEAM(TEAMID, NAME, CITY)
- PLAYER(PLAYERID, NAME_SURNAME, BIRTH_DATE, TEAMID)
- MATCH(ROUND_NUM, PAIR_NUM, HOME_TEAM, AWAY_TEAM, DATE, TOTAL_HOME, TOTAL_AWAY)
- MATCH_PLAYER(ROUND_NUM, PAIR_NUM, PLAYERID, MINUTES_PLAYED)
- MATCH_STATS(ROUND_NUM, PAIR_NUM, TIME, PLAYERID, EVENT)
(Note: EVENT attribute can contain the following values: "GOAL", "OWN GOAL", "YELLOW CARD", "RED CARD". TIME attribute is of type INTERVAL MINUTE TO SECOND.)

Write SQL:1999 commands that:
- a) Display statistical data about players of football club "PARTIZAN" for the match played in the 4th round (display minutes played for all club players). OR a) Display data about players of football team "Real Madrid" who did NOT play in the 7th round match.
- b) Display the best scorers by rounds played (display round number, player name_surname, team name and number of goals scored). The best scorer is the player who scored the most goals in the match (there can be multiple such players).
- c) Create a "LEAGUE_TABLE" view containing Team_Name, TotalPoints, ScoredGoals, ConcededGoals, Goal_Difference, MatchesPlayed, which displays the football team name, points earned based on match results (if match result is a draw, teams get 1 point each, winner gets 3 points, loser gets 0 points), data on total scored and conceded goals, goal difference, and number of matches played.

# 7. Public Transportation System
## Exercises
Given relational schema:
- VEHICLE(VehicleCode, VehicleType)
- ROUTE(RouteNumber, StartStation, EndStation)
- STATION(StationCode, StationName)
- ROUTE_STATIONS(RouteNumber, StationCode, SEQ_NUM)
- DEPARTURE(VehicleCode, RouteNumber, DateTime, Status)
VehicleType in ('Bus', 'Tram', 'Trolleybus') Status in ('Successful', 'Cancelled', 'Delayed') SEQ_NUM in route defines the order of stations on the route

Write SQL:1999 commands that:
- a) Display VehicleCode, VehicleType, Date and Time on route 18, between 13:00 and 17:00 hours for April 1st and 7th, 2003 where the departure was cancelled (Status attribute).
- b) Create a DailyDepartureSchedule view (RouteNumber, VehicleType, StartStationName, EndStationName, TotalVehicleCount) that displays planned daily vehicle departures for the current date.
- c) Display all data about the route, day and number of departures, for the route that had the fewest departures from the set of maximally realized routes by days in January of the current year. The maximally realized route for a specific day is the one with the highest number of realized departures.
- d) Provide an overview by quarters, then by vehicle types, total number of planned departures, number of successful departures, number of cancelled departures and number of delayed departures for 2002.

# 8. Component Management System
## Exercises
Given relational schema:
- COMPONENT_TYPE(TYPEID, NAME, DESCRIPTION)
- TYPE_ATTRIBUTES(TYPEID, ATTRIBUTEID, NAME, DOMAIN, REQUIRED)
- COMPONENT(COMPID, SERIALNUMBER, COMPONENTTYPE)
- COMPONENT_ATTRIBUTES(COMPID, ATTRIBUTEID, VALUE)
- CONNECTION(PARENT_COMPID, CHILD_COMPID)
- ASSEMBLY(COMPONENTID, NAME)

Write SQL:1999 commands that:
- a) Display all components and names and values of their required attributes that belong to component type named "AAA".
- b) Provide average, minimum and maximum values of all attributes with domain "INTEGER" for all component types.
- c) Create an INCORRECT_ATTRIBUTES view (COMPID, ATTRIBUTEID, ATTRIBUTE_NAME, ERROR) that displays all incorrectly entered attributes for each component. If a component is assigned an attribute that is not defined for the component type to which the component belongs, enter 'N/A' in the ERROR field. If a required attribute is not assigned to a component, enter 'REQUIRED' in the ERROR field.
- d) Insert into the ASSEMBLY relation all "primary" components that are not in the relation. Primary components are those that are not built into any assembly.

# 9. Library System
## Exercises
Given relational schema:
- BOOK(BOOK-ID, TITLE, YEAR_PUBLISHED, NUM_AUTHORS, NUM_COPIES)
- BOOK_COPY(BOOK-ID, INVENTORY-NUMBER, STATUS)
- AUTHOR(AUTHOR-ID, NAME)
- WROTE(BOOK-ID, AUTHOR-ID)
Write SQL:1999 commands that:
- a) For all authors, display the number of books they wrote. Sort the result by number of books.
- b) Display titles of books written by an odd number of authors and which exist in a larger number of copies (use data on number of copies from BOOK_COPY relation, use data on number of authors from WROTE relation).
- c) Check if the value of the NUM_AUTHORS attribute of the BOOK relation equals the number of tuples in the WROTE relation. If the attribute value is correct, the query should display the book title and text "Correct number of authors", otherwise the book title and text "Incorrect number of authors".

# 10. Hotel Management System
## Exercises
Given relational schema:
- HOTEL(HOTELID, NAME, ADDRESS, CITY, CLASS)
- ROOMTYPE(ROOMTYPEID, NAME, DESCRIPTION)
- ROOM(HOTELID, ROOMNUMBER, ROOMTYPE, STATUS)
- HOTEL_ROOMTYPE(HOTELID, ROOMTYPEID, TOTAL_ROOMS, PRICE)
- RESERVATION(HOTELID, SEQ_NUM, DATE_FROM, DATE_TO, ROOMTYPEID, STATUS, ROOMNUMBER)

Write SQL:1999 commands that:
- a) Display the following data about hotel capacities (hotelName, roomTypeName, numberOfRooms and roomPrice) for "3-star" hotels that have at least 2 single rooms. Sort the query result in descending order of "roomTypeName" and within them in ascending order of room prices.
- b) Create a view that displays for all cities the number of hotels by categories. The view contains the following attributes: cityName, hotelClass, totalNumberOfHotels, totalNumberOfRooms.
- c) Based on room data (ROOM relation), update the capacities of all hotels (attribute "TOTAL_ROOMS" of "HOTEL_ROOMTYPE" relation).

# 11. Supply Chain System
## Exercises
Given relational schema:
- SUPPLIER(SUP, SNAME, STATUS, CITY)
- CUSTOMER(CUS, CNAME, CITY)
- PRODUCT(PRD, PNAME, COLOR, WEIGHT)
- DELIVERY(SUP, PRD, CUS, DATE, QUANTITY)

Write SQL commands that:
- a) Display customer names and received quantities of yellow products for deliveries in 2000.
- b) Create an EXCHANGE view with attributes SNAME, SCITY, CNAME, CCITY that displays supplier name, supplier city, customer name and customer city, for suppliers and customers who had trade exchange in the current year but are not from the same city.
- c) Display names, cities and quantities for suppliers who delivered more than 100 pieces of product 'Philips TV 51' in the first quarter of the current year. Display the result in descending order of quantities.
- d) Write a program in C (exceptionally in pseudo code) that sets the STATUS attribute value to "HIGH" for suppliers who had more than 100 deliveries in the first quarter of the current year. (Note: The relational system supports only single-table queries.)