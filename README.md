# Age_Calculator
So there I basically create a age calculator using javascript

Certainly! Let's break down how the age is calculated in the `calculateage()` function:

1. **Date of Birth (DOB) Input**:
   - The function starts by taking the user's date of birth (DOB) as input.

2. **Extracting Components of DOB**:
   - It extracts the day, month, and year components from the DOB using the `Date` object.
     - `let d1 = dob.getDate();`: Extracts the day of the month.
     - `let m1 = dob.getMonth() + 1;`: Extracts the month (adjusted by 1 because months are zero-based in JavaScript).
     - `let y1 = dob.getFullYear();`: Extracts the year.

3. **Current Date**:
   - It gets the current date and time.

4. **Extracting Components of Current Date**:
   - It extracts the day, month, and year components from the current date using the `Date` object.
     - `let d2 = today.getDate();`: Extracts the current day of the month.
     - `let m2 = today.getMonth() + 1;`: Extracts the current month (adjusted by 1).
     - `let y2 = today.getFullYear();`: Extracts the current year.

5. **Calculating the Age**:
   - It initializes variables `d3`, `m3`, and `y3` to store the calculated age in days, months, and years.
   - It calculates the years by subtracting the birth year from the current year:
     - `y3 = y2 - y1;`

6. **Handling Months**:
   - It checks if the birth month (`m1`) is less than or equal to the current month (`m2`).
   - If the birth month is less than or equal to the current month, it calculates the months normally:
     - `m3 = m2 - m1;`
   - If the birth month is greater than the current month, it subtracts 1 year from the age and then adds 12 months to account for the months:
     - `y3--;`
     - `m3 = 12 + m2 - m1;`

7. **Handling Days**:
   - It checks if the birth day (`d1`) is less than or equal to the current day (`d2`).
   - If the birth day is less than or equal to the current day, it calculates the days normally:
     - `d3 = d2 - d1;`
   - If the birth day is greater than the current day, it subtracts 1 month from the age and then calculates the days by considering the number of days in the previous month:
     - `m3--;`
     - It calls the `getdaysinmonth()` helper function to get the number of days in the birth month and adds it to the current day (`d2 - d1 + getdaysinmonth(d1, y1)`).

8. **Adjusting Negative Months**:
   - It checks if `m3` is negative, indicating that the birth month was in the future compared to the current month. In this case, it adjusts the months and years accordingly:
     - `m3 = 11;`
     - `y3--;`

The age is then calculated in years, months, and days and stored in the variables `y3`, `m3`, and `d3`. This algorithm handles cases where the birth date is before or after the current date in the same year or month, ensuring an accurate age calculation.
