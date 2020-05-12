# Unit Testing Documentation template



# Contents

- [Black Box Unit Tests](#black-box-unit-tests)







# Black Box Unit Tests: Exercise 1

 
**Criteria for method orderIntegers(int v[]):**


- Length of the input vector (number of its integer components) 

- Type of parameter passed to orderIntegers (integers, all other types)




**Predicates for method orderIntegers(int v[]):**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Length of the input vector          | different from 3         |
|                           | =3          |
| Type of parameter passed to orderIntegers         | integers     |
|                           | all other types        |




**Boundaries for method orderIntegers(int v[]):**

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Length of the input vector     | 0, 1, 2, 3, 4, maxsize-1, maxsize|
| Type of parameter passed to orderIntegers | |





 **Combination of predicates for method orderIntegers(int v[])**

| Lenght of input vector | Type of parameter passed to orderIntegers | Valid/Invalid | Description of the test case| JUnit test case     |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- |
| Different from 3          | -        | I     |  int v[]=[1,2,3,4];<br /> orderIntegers(v)--> Exception     | com.polito.exercise1.blackboxtests.tc1     | 
| = 3          | integer        | V    |  int v[]=[5,-2,8];<br /> orderIntegers(v) --> [8,5,-2] , 8     | com.polito.exercise1.blackboxtests.tc2     |
|              | all other types        | I  |  double v[]=[1.3,2.3,3.4];<br /> orderIntegers(v) --> Exception     | com.polito.exercise1.blackboxtests.tc3     |  


<br />

# Black Box Unit Tests: Exercise 2

**Criteria for method acceptableToEat:**


- Type of parameters passed to acceptableToEat

- Total amount of calories

- Constraint (carb + protein ) / fat
<br />

<br />

**Predicates for method acceptableToEat:**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Type of parameters for acceptableToEat         | integer          |
|                           | all other types          |
| Signs of input parameters  | all Positive |
|                            |at least one negative|
| Total amount of calories  | <1000      |
|                           | >=1000         |
| Constraint (carb + protein ) / fat| >0.5          |
|                           | <=0.5           |



<br />

**Boundaries for method acceptableToEat**:

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Type of parameters for acceptableToEat    | |
| Signs of input parameters  | 0, -1, 1 |
| Total amount of calories| 0,1, 999,1000,1001, maxint-1, maxint|
| Constraint (carb + protein ) / fat| 0, 0.01, 0.49 0.50, 0.51, maxdouble-0.01, maxdouble|

**REMARK**: i assumed that the precision of last constraint is 0.01, because in the text of exercise 2, there isn't nothing about this fact.

<br />

 **Combination of predicates for method acceptableToEat**

| Type of parameters for acceptableToEat | Signs of input parameters|Total amount of calories | Constraint (carb + protein ) / fat | Valid/Invalid | Description of the test case | JUnit test case |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | ------------------------------------------------------------ |----|
| Integer          |  All positive| <1000         |  >0.5         | V          | acceptableToEat(1,1,1) --> true                                     | com.polito.exercise2.blackboxtests.tc1 |
|      | |       |  <=0.5         | V            | acceptableToEat(1,1,10) --> false | com.polito.exercise2.blackboxtests.tc2 |
|      ||>=1000        |  -       | V            | acceptableToEat(100,100,100) --> false | com.polito.exercise2.blackboxtests.tc3 |
|      |at least one negative|-        |  -       | I            | acceptableToEat(-1,1,1) --> Exception | com.polito.exercise2.blackboxtests.tc4 |
| All other types        |-| -         |  -        | I | acceptableToEat(98.2,34.4,76.3) --> Exception|com.polito.exercise2.blackboxtests.tc5 |


# Black Box Unit Tests: Exercise3

**Criteria for method parallelogram:**


- Type of parameters passed to parallelogram

- Sign of input parameters



<br />

**Predicates for method parallelogram:**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Type of parameters passed to parallelogram         | Integer          |
|                           | all other types          |
| Signs of input parameters          |All positive      |
|                           | at least one negative         |
| (slope of P1P3)= (slope od P2P3) and <br /> (slope of P1P2) = (slope od P3P4)      |yes      |
|                           | no        |
|All four points are different| yes|
|                             | no|

**REMARK**: the points P1, P2, P3, P4 are the same of the exercise 3 picture, so: P1(x1,y1), P2(x2,y2), P3(x3,y3), P1(x4,y4).  <br /> Moreover the slopes above mentioned are defined as follow:  <br />
slope of P1P3=(y3-y1)/(x3-x1) <br />
slope of P2P3=(y3-y2)/(x3-x2) <br />
slope of P1P2=(y2-y1)/(x2-x1) <br />
slope of P3P4=(y4-y3)/(x4-x3) <br />
Finally i have assumed that the square is a particular case of parallelogram.


<br />

**Boundaries for method parallelogram**:

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
|Type of parameters passed to parallelogram   |           |
| Signs of input parameters  | 0, -1, 1 |
| (slope of P1P3)= (slope od P2P3) and <br /> (slope of P1P2) = (slope od P3P4)      ||
|All four points are different||


<br />
<br />

 **Combination of predicates for method parallelogram**

| Type of parameters passed to parallelogram  | Signs of input parameters|All four points are different|(slope of P1P3)= (slope od P2P3) and <br /> (slope of P1P2= slope od P3P4)| Valid/Invalid | Description of the test case | JUnit test case |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | -------- |-----|
| Integer          | All positive      |yes|yes|  V             | parallelogram(0,3,1,4,0,0,6,6) --> 18| com.polito.exercise3.<br />blackboxtests.tc1 |
|         |       ||no|  V             | parallelogram(0,3,0,2,0,0,3,2) --> -1| com.polito.exercise3.<br />blackboxtests.tc2 |
|           |       |no|-|  V             |parallelogram(0,3,0,0,0,0,3,0) --> -1| com.polito.exercise3.<br />blackboxtests.tc3 |
|           | at least one negative      |-||V             |parallelogram(0,0,0,-2,0,3,3,2) --> -1 | com.polito.exercise3.<br />blackboxtests.tc4 |
| All other types          | -       |-| |V             | parallelogram(1.2,4.3,5.6,2.4,6.7,2.5,3.6,2.7) --> -1| com.polito.exercise3.<br />blackboxtests.tc5 |


# Black Box Unit Tests: Exercise4

### public class Item { 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private String itemCode;  \\\ item number <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private int availability; <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private String description; <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private String name; 
### }
### public class Inventory{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; void addItem(Item i) throws ItemAlreadyExists, InventoryOverflow; <br /> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Item searchItem (String itemCode) throws ItemNotExists; <br /> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; public new Item(String itemCode,int quantity);  <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; int availabilityItem (String itemCode) throws ItemNotExists; <br /> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; void subtractItem (String itemCode) throws ItemNotExists, ItemNotAvailable; <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; void addQtyToItem(String itemCode, int qty_to_add); <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; void subtractQtyToItem(String itemCode, int qty_to_subtract);
### }


**Criteria for method addItem:**

- Type of parameter for addItem

- Item already exists

- Total number of items in the inventory


**Criteria for searchItem and availabilityItem methods:**
- Type of parameter for searchItem and availabilityItem methods

- Item not exists

**Criteria for method new Item:**
- Couple of types of parameters (in oreder) for new Item 

- Sign of quantity

**Criteria for method subtractItem:**
- Type of parameter for subtractItem

- Item not exists

- Item not available

**Criteria for addQtyToItem and subtractQtyToItem methods:**

- Couple of types of parameters (in oreder)

- Qunatity of item (availability attribute)

- Item not Exists

<br />

**Predicates for all methods:**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
|Item already exists|yes|
|                   |no|
|Type of parameters <br /> (for searchItem method,availabilityItem <br /> and subtractItem methods)|String|
|                                                                     |All other types|
|Item not exists|yes|
|               |no|
|Couple of types of parameters in order <br /> (for new Item, addQtyToItem and <br /> subtractQtyToItem methods) |(String, Integer)|
|                                           |All other combinations of two types|
|Item not available|yes|
|                  |no|
|Total number of items in the inventory|0 to maxNumber|
|                                      |maxNumber+1 and above|
|Quantity of item (availability attribute) | under 0 |
|                                          | 0 to maxQuantity|
|                                          | maxQuantity+1 and above|
|Sign of quantity| positive |
|                | negative |

<br />

**Boundaries for all methods**: <br />
<br /> Are shown only the relevant criteria for the boundary;

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Total number of items in the inventory  | 0,1, maxNumber-1,maxNumber, maxnumber+1, maxint-1,maxint|
|Quantity of item (availability attribute)|minint,minint+1,-1,0,1, axQuantity-1,maxQuantity,maxquantity+1, maxint-1, maxint|
|Sign of quantity| -1,0,1|

<br />

**Combination of predicates for method new Item**

|  Couple of types of parameters (in oreder) |Sign of quantity| Valid/Invalid | Description of the test case                                 | JUnit test case (T implies calling the <br /> constructor in the Inventory class)                               |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | ------------------------------------------------------------ | 
|  (String,Integer) | positive   |    V     | Item item= new Item(""+1,3);| com.polito.exercise4.<br />blackboxtests.tc1|
||negative|I|Item item= new Item(""+1,-3); --> Error;|com.polito.exercise4.<br />blackboxtests.tc2 |
|  All other combinations of two types | -   |    I     | i.availabilityItem("phone", 3.5)--> Error; | com.polito.exercise4.<br />blackboxtests.tc3 |

<br />

**Combination of predicates for method addItem**

| Type of the input parameter for addItem| Item already exists |Total number of items in the inventory | Valid/Invalid | Description of the test case                                 | JUnit test case                                |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | ------------------------------------------------------------ | -------------------------------------------- |
| Item          | no         | maxNumber+1 and above    |    I     | for(j=1; j<= maxNumber; j++){<br /> Item item= new Item(""+j,0); <br />i.addItem(item);<br />}<br />Item item= new Item(""+maxNumber+1,0); <br /> i.addItem(item)-->InventoryOverflow; | com.polito.exercise4.<br />blackboxtests.tc4 |
|||0 to maxNumber|V|for(j=1; j<= maxNumber-1; j++){<br />Item item= new Item(""+j,0); <br />i.addItem(item);<br />}<br /> Item item= new Item(""+maxNumber,0); <br /> i.addItem(item); | com.polito.exercise4.<br />blackboxtests.tc5 |
||yes|-|I|Item item= new Item(maxNumber,0); <br />i.addItem(item);<br /> i.addItem(item) --> ItemAlreadyExists; | com.polito.exercise4.<br />blackboxtests.tc6 |
|All other types|-|-|I|i.addItem("phone")--> Error;| com.polito.exercise4.<br />blackboxtests.tc7 |

<br />

**Combination of predicates for method searchItem**

|  Type of input parameter |Item not exists| Valid/Invalid | Description of the test case                                 | JUnit test case (T implies calling the <br /> constructor in the Inventory class)                               |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | ------------------------------------------------------------ | 
|  String | no   |    V     | Item item= new Item(""+1,0); <br />i.searchItem(""+1) --> item; | com.polito.exercise4.<br />blackboxtests.tc8 |
||yes|I|i.searchItem(""maxNumber+10) --> ItemNotExists;|com.polito.exercise4.<br />blackboxtests.tc9 |
|  All other combinations of two types | -   |    I     | i.searchItem(113)--> Error; | com.polito.exercise4.<br />blackboxtests.tc10 |

<br />

**Combination of predicates for method availabilityItem**

|  Type of input parameter |Item not exists| Valid/Invalid | Description of the test case                                 | JUnit test case (T implies calling the <br /> constructor in the Inventory class)                               |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | ------------------------------------------------------------ | 
|  String | no   |    V     | Item item= new Item(""+1,0); <br /> availablity(""+1) --> 0 | com.polito.exercise4.<br />blackboxtests.tc11 |
||yes|I|i.searchItem(""+maxNumber+10) --> ItemNotExists;|com.polito.exercise4.<br />blackboxtests.tc12 |
|  All other combinations of two types | -   |    I     | i.availabilityItem(115)--> Error; | com.polito.exercise4.<br />blackboxtests.tc13 |

<br />

**Combination of predicates for method subtractItem**

|  Type of input parameter |Item not exists|Item not available|Valid/Invalid | Description of the test case | JUnit test case (T implies calling the <br /> constructor in the Inventory class)                               |
| ---------------- | ---------------- | --- |------------------------- | ------------------- | ------------- | ------------------------------------------ | 
|  String | no   | no |   V     | Item item= new Item(""+1,1); <br /> i.subtractItem(""+1); | com.polito.exercise4.<br />blackboxtests.tc14 |
|  |   | yes |   I     | Item item= new Item(""+1,0); <br /> i.subtractItem(""+1)--> ItemNotAvailable; | com.polito.exercise4.<br />blackboxtests.tc15 |
|  |   yes | - |   I    | i.subtractItem(""+maxNumber+10) --> ItemNotExists; | com.polito.exercise4.<br />blackboxtests.tc16 |
|  All other types |   - | - |   I     | i.subtractItem(123.45)--> Error; | com.polito.exercise4.<br />blackboxtests.tc17 |

<br />

**Combination of predicates for method addQtyToItItem**

|  Couple of types of parameters (in oreder) |Item not exists|Qunatity of item (availability attribute)|Valid/Invalid | Description of the test case | JUnit test case (T implies calling the <br /> constructor in the Inventory class)                               |
| ---------------- | ---------------- | --- |------------------------- | ------------------- | ------------- | ------------------------------------------ | 
|  (String,Integer) | no   | 0 to maxQuantity |   V     | Item item= new Item(""+1,0); <br /> for(j=1; j<=maxQuantity; j++){<br /> i.addQtytoItem(""+1, 1);} | com.polito.exercise4.<br />blackboxtests.tc18 |
|  |   | maxQuantity+1 and above |   I     |Item item= new Item(""+1,0); <br />  for(j=1; j<=maxQuantity; j++){<br /> i.addQtytoItem(""+1, 1);}<br /> i.addQtyToItem(""+1,1); --> Error  | com.polito.exercise4.<br />blackboxtests.tc19 |
|  |  yes | - |   I     | i.addQtyToItem(""+maxNumber+1,1) --> ItemNotExists| com.polito.exercise4.<br />blackboxtests.tc20 |
|All other couple types of parameters  | - | - |   I     | i.addQtyToItem("phone",1.5) --> Error| com.polito.exercise4.<br />blackboxtests.tc21 |

<br />

**Combination of predicates for method subtractQtyToItItem**

|  Couple of types of parameters (in oreder) |Item not exists|Qunatity of item (availability attribute)|Valid/Invalid | Description of the test case | JUnit test case (T implies calling the <br /> constructor in the Inventory class)                               |
| ---------------- | ---------------- | --- |------------------------- | ------------------- | ------------- | ------------------------------------------ | 
|  (String,Integer) | no   | 0 to maxQuantity |   V     | Item item= new Item(""+1,maxQuantity); <br /> for(j=1; j<=maxQuantity; j++){<br /> i.subtractQtytoItem(""+1, 1);} | com.polito.exercise4.<br />blackboxtests.tc22 |
|  |   | under 0|   I     | Item item= new Item(""+1,maxQuantity); <br />  for(j=1; j<=maxQuantity; j++){<br /> i.subtracttoItem(""+1, 1);}<br /> i.subtractQtytoItem(""+1,1); --> Error  | com.polito.exercise4.<br />blackboxtests.tc23 |
|  |  yes | - |   I     | i.subtractQtytoItem(""+maxNumber+1,1) --> ItemNotExists| com.polito.exercise4.<br />blackboxtests.tc20 |
|All other couple types of parameters  | - | - |   I     | i.subtractQtytoItem("phone",1.5) --> Error| com.polito.exercise4.<br />blackboxtests.tc24 |
