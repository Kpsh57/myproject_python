# myproject_python
# Objective: Write to display a food menu to the user, asks him to select the food & quantity that he wants to buy and calculates the amount he must pay for the food.

# User is prompted to input his choice of food, given the 3 options (i.e. Option1: Muffin, Option2: Pancakes or Option3:Hashbrown) 

print('''Welcome to ABCcafe!
Below is our Breakfast menu:
1.Muffin ($5.00) 2.Pancakes ($3.00) 3.Hashbrown ($1.50)''')     
menu = input("Enter your choice of food: ")                    

# Thereafter, user is required to input the quantity of his chosen food. The below codes will calculate the total costs & displays total amount payable by user.
# But if user did not input option 1, 2 or 3, an error message will be display. 

if menu == "1" or menu == "2" or menu == "3":
    if menu == '1':
        print("Muffin $5.00 is added!")                     
        qty = int(input("How many Muffins do you want to order?: "))              
        print(f'The total cost for {qty} Muffin is ${qty*5:.2f}')                 
    elif menu == '2':
        print("Pancakes $3.00 is added!")     
        qty = int(input("How many Pancakes do you want to order?: "))             
        print(f'The total cost for {qty} Pancake is ${qty*3:.2f}')                
    elif menu == '3':
        print ("Hashbrown $1.50 is added!")
        qty = int(input("How many Hashbrowns do you want to order?: "))          
        print(f'The total cost for {qty} Hashbrown is ${qty*1.50:.2f}')                 
else: 
    print("Sorry, you have entered an invalid choice.Unable to continue. Exiting program.... ")   
