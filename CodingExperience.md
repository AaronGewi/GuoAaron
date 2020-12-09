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
- Random Read File
```
#Import random
import random


#Create a main function
def main():

    #Create and open a file in write mode
    writefile = open("randomnum.txt", "w")


    # Ask the user for how many numbers they want

    while (True):
        try:
            number_amount = int(input("How many random numbers do you want?: "))
            if (number_amount < 0):
                print("Negative times are not allowed.")
                continue
        except ValueError:
            print("The value you entered is invalid.  Only numerical values are valid.")
        else:
            break

    #Ask for the lowest random number
    while (True):
        try:
            lowest_number_amount = int(input("What is the lowest the random number should be: "))
        except ValueError:
            print("The value you entered is invalid.  Only numerical values are valid.")
        else:
            break

    #Ask for the highest random number
    while (True):
        try:
            highest_number_amount = int(input("What is the highest the random number should be: "))
        except ValueError:
            print("The value you entered is invalid.  Only numerical values are valid.")
        else:
            break



    #Apply the function
    for counter in range(number_amount):
        randomNumber = random.randint(lowest_number_amount, highest_number_amount)
        writefile.write(str(randomNumber) + "\n")

    #Print the function
    print("\n")
    print(number_amount, "numbers have been written to the file randomnum.txt")

    #Close the file
    writefile.close()
    print("\nThe program has ended")


#Call the function
main()
```
- Object Position Calculator
```
def main():
    # Get Users initial position
    while (True):
        try:
            initial_x_position = float(input("Enter the object's initial position: "))
        except ValueError:
            print("The value you entered is invalid. Only numerical values are valid.")
        else:
            break

    #Get Users Initial Velocity
    while (True):
        try:
            initial_v_velocity = float(input("Enter the object's initial velocity: "))
        except ValueError:
            print("The value you entered is invalid. Only numerical values are valid.")
        else:
            break

    #Get Users Acceleration
    while (True):
        try:
            acceleration = float(input("Enter the object's acceleration: "))
        except ValueError:
            print("The value you entered is invalid. Only numerical values are valid.")
        else:
            break

    #Get Users Time
    do_time = True
    while (do_time):
        try:
            time = float(input("Enter the time elapsed: "))
        except ValueError:
            print("The value you entered is invalid. Only numerical values are valid.")
            continue

    #Make sure that the time cannot be negative
        try:
            if (time < 0):
                print("Negative initial positions are not allowed.")
                continue
        except ValueError:
                print("The value you entered is invalid. Only numerical values are valid.")
        else:
              do_time = False

    #Print the final position
    final_position = str(initial_x_position + initial_v_velocity  * time + 0.5 * acceleration * time**2)
    print("\n")
    print("Your final position is " + final_position)

    #Ask if the user wants to do another calculation
    do_calculation = True
    while (do_calculation):

        another_calculation = input("Do you want to perform another calculation? (y/n): ")
        if (another_calculation != "y"):
            do_calculation = False
        if(another_calculation == "y"):
            main()

#Start the function
main()
```
- Turtle Graphics
```
import turtle
import math

def draw_sine(amplitude, start_x, end_x):

    x = start_x
    delta_x = 5
    y = 0

    turtle.penup()
    turtle.goto(start_x,0)
    turtle.pendown()

    while(x < end_x):
        y = amplitude * math.sin((2 * math.pi * frequency * x)/500)
        turtle.goto(x,y)
        x += delta_x
        #set the canvas size
def main():
        turtle.setup(800,800)
        start_x = -400
        end_x = 400
        draw_sine(200, 2, start_x, end_x)


main()
```

### Links to Other Pages
- [Home](https://github.com/AaronGewi/GuoAaron/blob/main/README.md)
- [About Me](https://github.com/AaronGewi/GuoAaron/blob/main/AboutMe.md)
- [Hobbies](https://github.com/AaronGewi/GuoAaron/blob/main/Hobbies.md)
- [My Shoes and Pictures](https://github.com/AaronGewi/GuoAaron/tree/main/My%20Shoes)

