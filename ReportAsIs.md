Model of Organization – as is

# Identification

Pizzeria Giusti, Nichelino (TO)

xxxxxxxxx (ex partita iva, codice fiscale, ..)

56.10.20

# Financial and legal information

Legal form (ex srl, snc, sas, plc, co, …)

Turn over year 2018
about 350.000€

# Organizational variables

## Size

3 employees full time (pizza chefs and owners of the company)
3 employees full time (delivery man/cashier)
6 employees part time 50% (delivery man)
6 employees part time 10% ("jolly" delivery man)

3+1,5+3+0,6 = 8,1

8,1 FTE, year 2018

## Products, services

Pizzeria take away and delivery.

## Goal, goal type, mission, vision, strategy

### Goal

Italian pizza at good price and fast delivery

### strategy

#### Porter 

|        | Low cost | Uniqueness |
| ------ | -------- | ---------- |
| wide   | X        |            |
| narrow |          |            |

Strategy: low cost and fast delivery

## Culture

### Assumptions
 
 - "We always did it like this and it always worked"
 - "Not big deal if we can not deliver the right product (pizza)"
 - "It's better to have less employees than needed offering a low quality service/product than hiring more employees"
 - "to pay employees as few as possible"
 - "It's better to be unable to offer some products than stocking raw materials risking to waste money"

## Structure

Organizational chart

```plantuml
@startwbs
* main organization
** Pizza chef (owner of the pizzeria 1)
*** Delivery man
*** Cashier
** Pizza chef (owner of the pizzeria 2)
*** Delivery man
*** Cashier
** Pizza chef (owner of the pizzeria 3)
*** Delivery man
*** Cashier
@endwbs
```
It is important to notice that the three pizzerias have no mechanism or office dedicated to horizontal communication, instead the owners use phone calls to communicate if something is out of stock in one of the branches to get it from one of the other two, so no information is stored about it. Accounting is done by counting the money by hand at the end of the day by the product owner.

### Type of structure

**Geografical**

Every function is replicated in all pizzerias: Management (done by the owners), accounting (done by the owner), manufactoring (pizza chef), marketing (deliverer also distributes advertisement letters), customer service (getting orders, done by the cashier).

### IT/IS  group / office


There is no IT/IS office.
The IT part of this organization is an external online food order service (just eat).


The activities for inventory, accounting and restock are managed by the pizza chef (producing only handwritten notes on paper) 


estimation of expense in IT/IS:
just eat fees = about 20% <br>
just eat ratio = just eat orders/tot orders = about 25% <br>
expense in IT (fees)= just eat fees * just eat ratio * turnover = 0,20 * 0,25 * 350000 = 17500 € per year <br>

num working days in a year = about 330 days <br>
Person hours for IT/IS per working day = about 6 hours (considering order management and inventory) <br>
Salary [€/hours] = 7€/hours <br>
expense in IT (employees) = Salary * person hours per working day * num working days in a year = 7 * 6 * 330 = 13860€ per year <br>
Report ratio: expense in IT / Turn over

## Formalization / specialization/ centralization

**Formalization:** low level of formalization, there aren't any specific standards or documents for this kind of activity (except for HACCP procedures)

**Specialization:** most of the task can be performed by every employee but some specific tasks like cooking pizzas require specific skills so can be performed only by a sub-group of employees (the owners)

**Centralization:** There is no centralization since all of the branches have their owner that has complete freedom over the management of their branch.

## Organizational type

Argument if organization is: mechanical / learning

Argument if organization is: entrepreneurial start up / divisionalized bureaucracy / etc

# Business Model Canvas

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
<tbody>
  <tr>
    <td class="tg-0pky" rowspan="2"><span style="font-weight:bold">Key partnerships</span><br>- Flour, vegetabe and meat suppliers.<br>- JustEat</td>
    <td class="tg-0pky"><span style="font-weight:bold">Key activities</span><br>Manufactoring (producing pizzas) <br>Logistic (Delivering)</td>
    <td class="tg-0pky" rowspan="2"><span style="font-weight:bold">Value Proposition</span><br>Low-cost italian pizza at home with a reliable and fast delivery service <br> (serving only orders within a certain range from the three restaurants) <br><br> 'Order and forget, relax'</td>
    <td class="tg-0pky"><span style="font-weight:bold">Customer Relationship</span><br> self service (call restaurant if there is problem) </td>
    <td class="tg-0pky" rowspan="2"><span style="font-weight:bold">Customers segments</span><br>People used to eat ordered pizza at home</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:bold">Key Resources</span><br>- Restaurants<br>- Inventory of Ingredients for pizza production<br>- Inventory of drinks
    <br>- Delivering Cars</td>
    <td class="tg-0pky"><span style="font-weight:bold">Channels</span><br>Restaurants (face to face interaction customer-cashier), Phone lines advertised by paper flyers, food delivery application NOT managed by the company (JustEat)</td>
  </tr>
  <tr>
    <td class="tg-0pky" colspan="2"><span style="font-weight:bold">Cost Structure</span><br>Restaurants, Employees, Ingredients, JustEat fees</td>
    <td class="tg-0pky" colspan="3"><span style="font-weight:bold">Revenue Streams</span><br>Sales of pizzas and drinks</td>
  </tr>
</tbody>
</table>
Remark: key processes box must be consistent with IS Views /  Process view (below)

# IS Views

TODO:
## Functional view, data


TODO:

UML class diagram for data conceptual model (common to all processes / all organization)

## Functional view, processes

List and describe key processes


| Process name                      | Description (text)                                                               | Input                           | Output                                |
| --------------------------------- | -------------------------------------------------------------------------------- | ------------------------------- | ------------------------------------- |
| **Inventory / restock**           | Check the missing ingredients, buy them and restock theinventory                 | ingredients request             | inventory restocked                   |
| **Get new order**                 | Customer requests products, all the informations are written in the order ticket | order request                   | order ticket                          |
| **Prepare products for an order** | Queue organization, Cook products and pack up them in pizza boxes                | order ticket                    | pizza ready to be delivered/picked up |
| Deliver order                     | Get the products ready to be delivered and ship them to the customer             | Products ready and order ticket | Product at customers house            |

(must be consistent with key processes box in BMC)

(corresponds to Process 'identification' step, see chapter 'Process redesign' in lessons )

For processes that will be changed in the transition to To Be report BPMN model

### BPMN

#### Invetory restock
![restock bpmn](./images/BPMN_ASIS_InventoryRestock.png)
#### Get new order

TODO:
#### Prepare products for an order

TODO:
## IT  view

TODO:
### Application portfolio

TODO:

List IT applications or services used

| Application name | Vendor (or internal if made internally) | Main functions |
| ---------------- | --------------------------------------- | -------------- |
|                  |                                         |                |



### Technological view

TODO:

UML deployment diagram, showing computational nodes, and allocation of applications + data clusters to nodes

(data clusters == group of classes, from the data model, UML class diagram)

(applications are the ones identified in application portfolio)

### Outsourcing

TODO:

Highlight which IT service is outsourced (if any)

# IT strategy

TODO:

Summarize the current IT strategy, discuss if it is consistent with the company strategy

# Indicators

TODO:

## CSF

CSF ( derived by us)

- CSF1 fast delivery time of the customer orders <br>
  - CSF11 response time to phone calls
  - CSF12 number of pizzas produced per week
  - CSF13 mean time to transport an order

- CSF2 quality of the product and service
  - CSF21 number of complaints from users
  - CSF22 ratings of reviews on JustEat

- CSF3 Marketing efficiency
  - CSF31 Number of new clients
  - CSF32 trend of sales
  - CSF33 delivered advertisement flyers


TODO:

| CSF ID | Type (domain, distinguishing, environment, contingency) | Textual description, link to strategy     | Related Metric(s)                                                                                     | Current value (if available) |
| ------ | ------------------------------------------------------- | ----------------------------------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------- |
| CSF1   | Buisness domain                                         | fast delivery time of the customer orders | - Response time to phone calls <br>- number of pizzas produced per week <br>- mean time to transport an order |        - 2 min <br>-  **X** pizza/week<br>- 8  min                  | 
| CSF2   | Buisness domain                                         | quality of the product                    | - complaints per week <br>-mean rating of JustEat reviews of last week<br> |   - **X** complaints/week <br>- **X** stars |
| CSF3   | Buisness domain                                         | Marketing efficiency                      | - new clients per week <br>  -sales per week<br>-number of distributed flyers per week                           |    - **X** clients<br>-**X** pizzas sold per week<br>- **X** flyers per week   |

## KPI

TODO:
### Process X

(Process name must be consistent with IS view / Process view)

KPI table for process X

| KPI name | KPI type (general, service..) | description | Unit of measure | CSF covered (if any) | Current value (if available) |
| -------- | ----------------------------- | ----------- | --------------- | -------------------- | ---------------------------- |
|          |                               |             |                 |                      |                              |

### Process Y

To be repeated for each relevant process (notably processes that will be changed in To Be)

# Summary analysis

TODO:

Critical points in the organization and their possible interaction with IS.

IT alignment problems.