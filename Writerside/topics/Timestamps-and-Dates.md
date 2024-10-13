# Timestamps and Dates

Timestamp is a combination of Date, Hour, Minutes Seconds and even Milliseconds.

To get the current timestamp, we can use the NOW() function.

```SQL
SELECT NOW();
```
![now](now.png)

To get a date out of the NOW() function, we cast the date as shown below:

```SQL
SELECT NOW()::DATE;
```
![now date](now-date.png)

To get the time, we simply cast the time as shown.

```SQL
SELECT NOW()::TIME;
```
![now time](now-time.png)

## Extracting specific fields from a timestamp
To extract specific fields from a timestamp, we can use the EXTRACT() method as shown:

Extracting year:
```SQL
SELECT EXTRACT(YEAR FROM NOW());
```
![extract year](extract-year.png)

Extracting the month:
```SQL
SELECT EXTRACT(MONTH FROM NOW());
```
![extract month](extract-month.png)

Extracting the day:
```SQL
SELECT EXTRACT(DAY FROM NOW());
```
![extract day](extract-day.png)

Extracting the day of the week:
```SQL
SELECT EXTRACT(DOW FROM NOW());
```

![extract the day of the week](extract-day-of-the-week.png)

0 means Sunday, 1 means Monday ... 6 means Saturday

Extracting the century:
```SQL
SELECT EXTRACT(CENTURY FROM NOW());
```

![extracting the century](extract-century.png)

Extracting hours
```SQL
SELECT EXTRACT(HOURS FROM NOW());
```

![extracting hours](extract-hours.png)

Extracting minutes
```SQL
SELECT EXTRACT(MINUTES FROM NOW());
```

![extract minutes](extract-minutes.png)

Extracting seconds
```SQL
SELECT EXTRACT(SECONDS FROM NOW());
```

![extract seconds](extract-seconds.png)

## Adding and Subtracting Dates
Assume we want to subtract 1 year from now, we use the INTERVAL keyword and then within quotes we specify the 
time as shown:

```SQL
SELECT NOW() - INTERVAL '1 YEAR';
```
![subtract 1 year](subtract-1-year.png)

If we want to subtract 20 years:

```SQL
SELECT NOW() - INTERVAL '20 YEARS';
```
![subtract 20 years](subtract-20-years.png)

If we want to subtract 1 month
```SQL
SELECT NOW() - INTERVAL '1 MONTH';
```
![subtact 1 month](subtract-1-month.png)

If we want to subtract 5 months
```SQL
SELECT NOW() - INTERVAL '5 MONTHS';
```
![subtract 5 months](subtract-5-months.png)

If we want to subtract 1 Day

```SQL
SELECT NOW() - INTERVAL '1 DAY';
```
![subtract 1 day](subtract-1-day.png)

If we wanted to subtract 3 days:
```SQL
SELECT NOW() - INTERVAL '3 DAYS';
```
![subtract 3 days](subtract-3-days.png)