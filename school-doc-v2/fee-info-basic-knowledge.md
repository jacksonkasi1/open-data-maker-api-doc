# Fee Info Basic knowledge

Here are the key fields from the CSV files to build a college tuition/fees API and MongoDB model:

**Useful Fields**

* UNITID - Unique college ID
* INSTNM - College name
* TUITION1-TUITION7 - Tuition rates for different categories
* FEE1-FEE7 - Fee rates for different categories
* HRCHG1-HRCHG7 - Per credit hour charges
* ISPROF1-ISPROF9 - Doctorate tuition rates
* ISPFEE1-ISPFEE9 - Doctorate fee rates
* OSPROF1-OSPROF9 - Out of state doctorate tuition rates
* OSPFEE1-OSPFEE9 - Out of state doctorate fee rates
* CHG1AT0-CHG1AT3 - In district tuition rates (2019-2023)
* CHG1AF0-CHG1AF3 - In district fee rates (2019-2023)
* CHG2AT0-CHG2AT3 - In state tuition rates (2019-2023)
* CHG2AF0-CHG2AF3 - In state fee rates (2019-2023)
* CHG3AT0-CHG3AT3 - Out of state tuition rates (2019-2023)
* CHG3AF0-CHG3AF3 - Out of state fee rates (2019-2023)
* CHG4AY0-CHG4AY3 - Books/supplies costs (2019-2023)
* CHG5AY0-CHG5AY3 - Room & board costs (2019-2023)
* CHG6AY0-CHG6AY3 - Other on-campus costs (2019-2023)
* CHG7AY0-CHG7AY3 - Off-campus room & board costs (2019-2023)
* CHG8AY0-CHG8AY3 - Off-campus other costs (2019-2023)
* CHG9AY0-CHG9AY3 - Off-campus with family other costs (2019-2023)

**Benefits**

* Allows searching colleges by name and location
* Retrieve tuition, fees, and other cost info by college
* Compare costs over time and across college categories
* Estimate total cost of attendance based on tuition, fees, room/board, etc
* Surface affordable college options based on cost data

