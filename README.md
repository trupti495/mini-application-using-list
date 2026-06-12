# mini-application-using-list
E-Cart aaplication using list
# mini application on list
#nested list
"""
View → Show all products available in the shop.
Add → Customer adds products to their cart (not to the shop inventory).
Buy → Display cart items and total bill.
Search → Search a product by name.
Delete → Remove a product from the cart.

"""
x=[[1,"car",500],
   [2,"doll",1000],
   [3,"grocery",2000],
   [4,"sunglasses",5000]]

cart = []

def view():
    print("id\tname\t\tprice")
    for i in range(len(x)):
        print(x[i][0], "\t", x[i][1], "\t", x[i][2])

def add():
    pid = int(input("Enter product id: "))

    for i in range(len(x)):
        if x[i][0] == pid:
            cart.append(x[i])
            print("Product added successfully")
            return

        else:
            print("Product not found")

def update():
    pid = int(input("Enter product id to update: "))

    for i in range(len(x)):
        if x[i][0] == pid:
            x[i][1] = input("Enter new product name: ")
            x[i][2] = int(input("Enter new product price: "))
            print("Product updated successfully")
            return

    print("Product not found")

def delete():
    pid = int(input("Enter product id to remove: "))

    for i in range(len(cart)):
        if cart[i][0] == pid:
            cart.pop(i)
            print("Product removed")
            return

    print("Product not found in cart")

def search():
    pid=int(input("enter ptoduct is :"))
    for i in range(len(cart)):
        if cart[i][0] == pid:
            print("product name:cart[i][1]")
            print("product price:cart[i][2]")
        else:
            print("product not found")    

def buy():
    total = 0

    if len(cart) == 0:
        print("Cart is empty")
        return

    print("ID\tNAME\t\tPRICE")

    for i in range(len(cart)):
        print(cart[i][0], "\t", cart[i][1], "\t", cart[i][2])
        total = total + cart[i][2]

    print("Total Bill =", total)
    print("Purchase Successful")
    
choice=0
while choice!=7:
 
 print("-----------ecart ----------\n")
 print("1.view products")
 print("2.add products")
 print("3.update products")
 print("4.delete products")
 print("5.buy products")
 print("6.search")
 print("7.exit")

 print
 choice=int(input("enter your choice: "))
 match choice:
    case 1:
        view()
    case 2:
        add()
    case 3:
        update() 
    case 4:
         delete()
    case 5:
         buy()
    case 6:
         search()     
    case 7:
         print(" you exit successfully !!!")                 
    case _:
        print("invalid choice")
