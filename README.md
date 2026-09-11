# Shawa-
trffvb
print("==================================================")
print("===================== WELCOME ====================")
print("=============== SHAWARMARK FOOD STORE ============")
print("==================================================")

print("========== OUR MENU ===================")
print("[SW] Shawarma Wrap:        -P80")
print("[SS] Shawarma Salad:       -P120")
print("[SB] Shawarma Burger:      -P70")
print("[ST] Shawarma Tacos:       -P85")
print("[SF] Shawarma Fries:       -P85")

food = input("Enter Food Code: ").upper()

if food == "SW":
    product = "Shawarma Wrap"
    price = 80
elif food == "SS":
    product = "Shawarma Salad"
    price = 120
elif food == "SB":
    product = "Shawarma Burger"
    price = 70
elif food == "ST":
    product = "Shawarma tacos"
    price = 85
elif food == "SF":
    product = "Shawarma Fries"
    price = 85
else:
    print("Invalid Code!")
    exit()

qty = int(input("Enter Food Quantity: "))

if qty <= 0:
    print("Invalid Food Quantity!")
    exit()
    
drinks = input("If you want add Drinks? (Y)Yes/(N)No: ").upper()

if drinks == "Y":
   print("======== OUR DRINKS ===================")
   print("[C] COKE:            -P20")
   print("[S] SPRITE :         -P20")
   print("[R] ROYAL:           -P20")
   print("[M] MOUNTAIN DEW:    -P25")
   print("[W] WATER BOTTLED:   -P15")
   
   choice = input("Choose Your Drinks Code: ")

   if choice == "C":
    drink_product = "Coke"
    drink_price = 20 
   elif choice == "S":
    drink_product = "Sprite"
    drink_price = 20 
   elif choice == "R":
    drink_product = "Royal"
    drink_price = 20
   elif choice == "M":
    drink_product = "Mountain Dew"
    drink_price = 25 
   elif choice == "W":
    drink_product = "Water Bottled"
    drink_price = 15
    
   else:
    print("Invalid Code!")
   
   quantity = int(input("Enter Drinks Quantity: "))

   if quantity <= 0:
    print("Invalid Drinks Quantity!")
    
    
elif drinks == "N":
   drink_product = "None"
   drink_price = 0
   quantity = 0
   subtotal_2 = 0
   print("No Drinks!")
   
else:
   print("Invalid Input! Enter (Y) or (N)")
   exit()
   
subtotal = price * qty
subtotal_2 = drink_price * quantity 
subtotal_3 = subtotal + subtotal_2 


if subtotal >= 1000:
    discount_rate = 0.12
elif subtotal >= 800:
    discount_rate = 0.05
else:
    discount_rate = 0

discount = subtotal * discount_rate
discount_amount = subtotal_3 - discount
tax = discount_amount * 0.12
final_total = discount_amount + tax

print("==================================================")
print("==================== RECIEPT =====================")
print("==================================================")
print(f"Product food   : {product}")
print(f"Price          : P{price:.2f}")
print(f"Quantity       : {qty}")
print(f"Subtotal food  : {subtotal:.2f}")
print("==================================================")
print(f"Product Drink  : {drink_product}")
print(f"Drink  Price   : P{drink_price:.2f}")
print(f"Drink Quantity : {quantity}")
print(f"Subtotal Drinks: {subtotal_2:.2f}")
print("==================================================")
print(f"Subtotal       : P{subtotal_3:.2f}")
print(f"Discount       : P{discount:.2f}")
print(f"Tax (12%)      : P{tax:.2f}")
print("==================================================")
print(f"Total Payment  : P{final_total:.2f}")
print("==================================================")

payment = float(input("Enter payment: P"))

if payment >= final_total:
    change = payment - final_total
    print(f"payment    :P{payment:.2f}")
    print(f"change     :P{change:.2f}")
else:
    balance = final_total - payment
    print("Insufficient payment!")
    print(f"Balance    :P{balance:.2f}")

print("==================================================")
print("================= THANK YOU ======================")
print("==================================================")
