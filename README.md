# FINAL-IRRR

# FUNCTIONNAL REQUAIRMENT
1 .the system can store products
2.system can  validate orders and checks stock
3.The system  should notifiy operators about important events 
4. The system sends pick tasks to the assigned robots and follows their progress
5. the system can decides number of robots needed
6. The system can  receives orders
7. the system  should check that every item is available and reserves it
8. Customers can browse items
9. customer can add products to a cart
10. Customers can track their order in real time
11. customer should be able to notified with the status of the order

# NON FUNCTIONAL REQUIARMENT
1 scalability : the system should handle growing numbers of users and requests
2 availability: the system should remain operational
3 low latancy :requestes should be processed quickly  read<1sec,writes<2sec
4 consistency and reliability : system should work correctely and consistncy
5 security: system should protect user data

# DATA MODEL
customer
{ 
id
username
password-hash
address
phone-number
}
warehouse
{
items
robots

}

Robots
{
status
location
battary level
}

notifacation
{
id
sender-id
customer-id
body
status
}

item
{
id
no-item
location
size
weight
}
order 
{
id
customer-id
item-id
status
}
Delivery 
{
order-id
customer-id

}

Task
 {
 robot-id
 status
 }

# API DESIGN
POST /items ->partial<item> 
{ title,
description,
price,
}

GET/items/{category}/{keyword}->list<items>
PATCH/orders/{orderid}->partial<order>
{status}
POST/orders->partial<order>
event listener ("send notification")->send notification
{
custumer-id,
content,
}
PATCH/tasks/{taskid}->partial<task>
{status}

Deep dives in the deepdives.txt file













