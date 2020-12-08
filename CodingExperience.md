# My Experience With Coding
> Prior to college, I didn't know much about coding. I knew what is was and what it was used for but I just had no clue on how coding works. It always seemed very intimidating to learn and i thought it was just too hard. I never even wrote my first line of code until I took this class. My first line of code was...

```
print("Hello World")
````

As this class and my other coding class continued I started to pickup and be able to write more and more code. With the help of [W3Schools](https://www.w3schools.com) and [Python](https://www.python.org/), I was eventually able to write full blocks of code. 

Here are some of the code that I have written this semester:
- Paint job Estimator
```
import math

# Get Users inputs

#Get the amount square feet
while (True):
    try:
        square_feet = float(input("What is the amount of square feet of walls: "))
        if (square_feet < 0):
            print("Negative initial positions are not allowed.")
            continue
    except ValueError:
        print("The value you entered is invalid. Only numerical values are valid.")
    else:
        break

#get price per gallon
while (True):
    try:
        gallon_price = int(input("What is the price per gallon of paint: "))
        if (gallon_price < 0):
            print("Negative initial positions are not allowed.")
            continue
    except ValueError:
        print("The value you entered is invalid. Only numerical values are valid.")
    else:
        break

#number of gallons of paint required
amount_of_gallons = float(square_feet * 1 / 350)
amount_of_gallons_rounded = (math.ceil(amount_of_gallons))
print(str("Amount of gallons of paint needed: " + amount_of_gallons_rounded)

#Hours of labor required
labor_hours = float(square_feet * 6/350)
print("Hours of labor required: ", format(amount_of_labor,".1f"))

#Cost of the paint
cost_of_paint = (amount_of_gallons_rounded * gallon_price)
print("Total cost of paint: " + cost_of_paint)

#Calculate labor charges
labor_charge = (amount_of_labor * 62.25)
print("The cost of labor would be: " + labor_charge)

#Calculate total cost
total_cost = (labor_charge + cost_of_paint)
```
- Number Stats
```
do_stat = True
while(do_stat):
        try:
            file = input("Enter file name: ")

    #set everything to zero first and set orgins
            number = open(file,"r")
            total = 0
            sum_total = 0
            max_value = int(number.readline())
            min_value = max_value
            number.seek(0)
            num_list = []
            num_dict={}

            for line in number:
    #Find the total
                total_numbers = int(line)
                num_list.append(total_numbers)
                total += 1

    #Find the Total of the values
                sum_total += total_numbers

    #Find the max and min
                max_value = max(max_value,total_numbers)
                min_value = min(min_value, total_numbers)

    #Find the Average
            average = sum_total/total
    #Find the range
            num_range = max_value - min_value

    #Find the median
            num_list.sort()
            n = len(num_list)
            if n % 2==0:
                median1 = num_list[int((n/2)-1)]
                median2 = num_list[int((n/2))]
                actual_median = (median1 + median2)/2
            else:
                actual_median = num_list[int(n/2)]

    #Find the mode
            for line in num_list:
                if line in num_dict:
                   num_dict[line] +=1
                else:
                    num_dict[line] = 1


            max_value = -1
            full_list=[]

            for line in num_dict:
                count = num_dict[line]
                if count > max_value:
                    max_value = count
                    full_list.clear()
                    full_list.append(line)
                elif count == max_value:
                    full_list.append(line)

            mode = full_list

    #Print everything
            print("File name: ", number.name)
            print("Sum: ", sum_total)
            print("Count: ", total)
            print("Maximum: ", max_value)
            print( "Minimum: ", min_value)
            print("Average: ", average)
            print("Median: ", actual_median)
            print("Mode: ", mode)
```
