## Buggy TLC

### Instructions
This document contains coding challenges to access a prospective developer's fit withing our organization.
As discussed, please find the attached coding challenge and email your solution to: niyi@joinbuggy.com, ziafat@joinbuggy.com
We'll get back to you with our decision after the review process.

Table Name: 'transaction'

| driver_name |   balance   | amount_paid |
|-------------|:-----------:|------------:|
| John Doe    |      389    |   200       |
| John Doe    |      389    |   200       |
| John Doe    |      389    |   200       |
| John Doe    |      389    |   200       |

**Database**

Write a query to return all transactions from the transaction table and group by driver_name.
How would you improve the table to be more efficient?

`[solution]`


**Python**

'''
Problem description:
  We have two driver objects created with a Driver class. Each driver is a customer in our company.
  The drivers are able to send payments to us through their bank account but we don't have an ID for their bank account on record so we don't know which of them is sending us what money.
  
  If the two drivers send payments to us, with an optional memo field,
  how do we handle matching the payments to the right driver?
  Please describe why you arrived at your solution.
'''

class Driver:
  def __init__(self,first_name,last_name,email,phone):
    self.first_name = first_name
    self.last_name = last_name
    self.email = email
    self.phone = phone
    self.owes = 0
    self.payments = []
  
  def get_balance(self):
    total_paid = 0
    for paid in self.payments:
      if "amount" in paid:
        total_paid += paid.get("amount")
    balance = self.owes - total_paid
    return balance

driver_a = Driver(first_name="Robert",last_name="Lang",email="robert@some_email.com",phone="9171231122")
driver_a.owes = 56
driver_b = Driver(first_name="Robert",last_name="Langdon",email="langdon@some_email.com",phone="3476567544")
driver_b.owes = 450
print(f"Driver A's name is {driver_a.first_name} {driver_a.last_name}, Balance is ${driver_a.get_balance()}")
print(f"Driver B's name is {driver_b.first_name} {driver_b.last_name}, Balance is ${driver_b.owes}")
print("\n")

new_payment_1 = {"type":"Zelle","amount":300,"date":"05-07-2020","memo":"Robert Langdon 546432"}
new_payment_2 = {"type":"Zelle","amount":450,"date":"05-07-2020","memo":""}

```

`[solution]`