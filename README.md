# Simplify
##############################################################################
##############Simplify Code 11.08.15 Written by Aidan O'Gorman################
##############################################################################
##############################################################################
##Concept: Simplify is a rota management tool which reduces the creation of###
##weekly staff rotas to a single click through the use of auto-generation.####
##The program will consist of a calender with the business's opening hours####
##along the vertical edge and the days of the week (date) along the ##########
##horizontal edge. The manager should be able to click "Auto-Generate" and ###
##have the software fill our their employee's hours for the week.#############
##############################################################################
##############################################################################

from random import randint
import calendar
import time

#Function 'emp_input' takes the names of manager and employees, stores them into
#the dictionary 'employee_list' and returns them (in random order) to the manager

def emp_input(i):
    
    employee = input("\nEnter employee name: ")       #Introduce 'import' function for companies with many employees
    working_hours = input("\nEnter employee's contracted hours per week: ")
    employee_list['Employee' + str(i)] = employee
    working_hours_list['Employee' + str(i)] = working_hours
        
    return employee_list


print ("Welcome to Simplify, a better way to manage your staff rotas!")

business_name = input("\nFirst, please tell us the name of your business: ")
managers_name = input("\nPlease enter the name of the store or business manager: ")

business_call = {}  #Separate list to store business details
manager_call = {}   #Separate list initialized to store manager's details

business_call['Business'] = business_name #Store the name of the business
manager_call['Manager'] = managers_name #Stores manager's name with a unique key


n = input("OK, let's get started. How many employees do you have? \n\nNumber of Employees: ")

employee_list = {} #Initializing the employee list
working_hours_list = {} # Initializing the working hours list (employee number is the same as in the employee list)

while True: #While loop which constantly returns to the beginning of the loop until the manager inputs a valid number
        if n.isnumeric():
            
            i=0 #Initializes the iterator

            for i in range(0,int(n)):
                emp_input(i)
            break
        
        else:
            n = input("Please try again: ")

#All employees stored in the system. Now to create the auto-generate feature#
            
x = randint(0,int(n)-1) #n is the number of employees in the store (Number starts at 0 but if a normal manager wants the first employee they'll type Employee 1.

print(employee_list['Employee' + str(x)]) #Prints a random employee name and contracted hours
print(working_hours_list['Employee' + str(x)]) #Prints the random employees' weekly working hours


