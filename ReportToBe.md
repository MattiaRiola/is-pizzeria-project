Model of Organization: To Be



# Summary of changes

Here describe at high level the change(s), and their motivation. Link with critical points identified in As Is analysis

**To contrast order loss and mischeduling of orders**
A web app will be developed to automatize and reduce human errors in the following events:
- A section of the web applications will be used by the pizza chef to signal the status empty/low/medium/full of the ingredients, this will be useful for:
  - Giving the cashier the ability to register only orders that can be satisfied reaching an agreement with the client at ordering time.
  - Automatically create a shopping list for the restock. 
- Orders will be registered by the cashier in the system with a dedicated form instead of writing the infos by hand on paper post-its.
- Registered orders will be visible by the pizza chef in the kitchen and automatically scheduled by the system 
- Orders information will be visible by the deliverers in a dedicated page of the webapp through their smartphones.
- Register customer to get customer informations only once in order to:
  - build loyalty of the customer by offering loyalty prizes.
  - speed up ordering process

# Organizational variables

Keep this section and subsections, if there is no change just write 'no change'.  In case there is a change detail it.

## Size
'no change'

## Products services
'no change'
## Goal, goal type, vision, mission, strategy
'no change'
## Culture
- "striving for customer satisfaction"
## Structure
'no change'
### IT office
Outsourced management of the application and technical assistance by IT consultancy company
## Formalization specialization centralization
'no change'
## Organizational type
'no change'
# Business model canvas

if there is no change just write 'no change'

other wise detail only the box(es) that change

**Key Partnership:**
- Added to the key partners the consultancy company that produces and maintain the web app

**Cost structure**
- Added to the cost structue the maintenance of the web app

**Key Resources**
- Added to the Key Resources the web app



# IS Views

## Functional view, data

Ticket order now have an additional field: customer number

@TODO: review this, is it necessary?  
Product has another link for substitue product chosen by the customer

Quantity in Ingredient (empty low  medium full)

```plantuml
@startuml
class TicketOrder {
  + delivery address
  + additional notes
  + time
  + order type: just eat or on site/phone call
  + payment: payed or to pay
  + status: queue/cooking/shipping/done
  + customer number
}

class Product {
  + type: food or drink
}

class Ingredient {
  + ID
  + name
  + quantity
}

Product "+" -- "*" TicketOrder : ordered in >
Ingredient "+" -- "*" Product 
@enduml
```

## Functional view, processes

Write no change if the model remains as in As Is

### Process selection

Report the PICK chart (see process redesign chapter)  used to select the process to be changed and argument about it

![PICK chart](./images/PICK_chart_TO_BE.jpg)

#### Inventory restock
![restock bpmn](./images/BPMN_TOBE_InventoryRestock.png)
- The shopping list is easier to do than in the ASIS scenario since the state of the product is continuously updated during working time
- The shopping list can be produced automatically by the system.
#### Get new order
![get new order bpmn](./images/BPMN_TOBE_GetNewOrder.png)
- Order is no more registered through a post it but instead is inserted in a form, leaving less space to human error (forgetting to ask for something) in getting the infos 
- The order can be composed only with products formed by ingredients that are available.
- A created order becomes now visible to the pizza chef automatically from a dedicated screen in the kitchen 
- Orders not being physical beings are now immune to loss or damage.
#### Queue management
![queue management bpmn](./images/BPMN_TOBE_QueueManagement.png)
- Differently from the ASIS scenario, this is completely automatized by the system.
#### Prepare order
![Prepare order bpmn](./images/BPMN_TOBE_PrepareProductsForAnOrder.png)
- since the system knows what products are produced with each ingredient, the chef can signal through a dedicated interface the unavailability of certain ingredients and the system will automatically compute the unavailability of the products communicating to Just Eat and the cashier interface.
- the order can be changed by the cashier through the interface.

#### Delivery
![delivery bpmn](./images/BPMN_TOBE_Delivery.png)
- the deliverer is less prone to lose ticket orders since are accessible via a dedicated section of the webapp, through their smartphone.

For each changed process report the new BPMN (highlight where are the changes and why) and  the software functions needed by the IS, as follows

| Activity in BPMN                                | Supporting Software functions                                                                                        |
| ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Register a ticket order                         | - show new ticket order form <br> - create new ticket order object                                                   |
| Show orders                                     | - get orders <br> - print order list <br> -show order details                                                        |
| Update order                                    | - setters for ticket order objects                                                                                   |
| Schedule orders                                 | - Priority queue list of ticket orders <br> - compute order priority by delivery time and estimated preparation time |
| Update ingredients availability                 | - setters for Ingredients                                                                                            |
| Show shopping list                              | - get list of orders with state different from "full"                                                                |
| Request product availability update in just eat | - Request to set product available/unavailable to Just Eat                                                           |
| Show order delivery info                        | - Get order delivery info                                                                                            |

## IT view

### Application portfolio

Write no change if the portfolio remains as in As Is

Otherwise list here the new portfolio, highlighting new applications, and abandoned applications

#### Selection

Describe the applications considered for the selection

| Application name             | Vendor    | Description                                                        | Price model and fees |
| ---------------------------- | --------- | ------------------------------------------------------------------ | -------------------- |
| SirioTrade                   | COMPASS   | Manages only accounting, orders at the table and menu composition. | fixed price          |
| Simphony POS for Restaurants | ORACLE    | Manages everything                                                 | time and material    |
| OpenBravo                    | OPENBRAVO | Manages everything                                                 | time and material    |

Describe here how the selection of the new application was made

| Criterion                 | SirioTrade | Simphony POS for Restaurants | OpenBravo |
| ------------------------- | ---------- | ---------------------------- | --------- |
| Inventory Management      |            | x                            | x         |
| Kitchen / Menu Management | x          | x                            | x         |
| Point of Sale (POS)       | x          | x                            | x         |
| Order List Management     |            | x                            |           |



**A custom made application is needed.** this conclusion is reached through the analysis of the competitors proposals. even though Simphony POS would cover all of our needs it would also mean for the pizzerias to buy IT hardware that supports it from ORACLE and this is an high money investment where the value is represented by the access to a lot of functions (Financial analysis, cloud hosting of records, table service assistance, ...) that the activity doesn't need. 

#### Coverage

Show how the selected application provides the software functions needed (as identified in Functional view, processes section), discuss gaps, if any

| Software function needed (from process view) | Software function provided by application selected | Gap analysis |
| -------------------------------------------- | -------------------------------------------------- | ------------ |
|                                              |                                                    |              |



### Technological view

Write no change in case. Otherwise report the new deployment diagram and highlight the changes

```plantuml
@startuml
node Just_eat_server
node Pizzeria_server
node Deliverer_smartphone
node Cashier_pc
node Chef_device

artifact JustEat_app
artifact browser
artifact PizzeriaManagmentApp

Just_eat_server -- Chef_device
Pizzeria_server -r- Just_eat_server
JustEat_app -u- Chef_device
Pizzeria_server -- Cashier_pc
Pizzeria_server -- Deliverer_smartphone
Pizzeria_server -- Chef_device 
Pizzeria_server -u- PizzeriaManagmentApp
[Deliverer_smartphone]  -- browser
Chef_device  -- browser
Cashier_pc  -- browser
@enduml
```

#### Integration

In case a new application is introduced discuss how integration happens in terms of

Data exchange (which data is exchanged)

Control mechanism (mechanism used by applications to interact, ex message passing, rpc, etc)

# IT strategy

Discuss if there should be changes to it.

# Effect of change(s)

## Effect on KPIs and CSFs

(remark, KPIs and CSFs should not depend on the change, but should remain the ones defined in the As Is section � the goal being to compare the effect of the change on the same indicators)

Report only indicators that are supposed to change, argument on why the change has an effect on them, report how much the indicator could change. Do not forget the unit cost of the product / service.

| Indicator (Csf, Kpi) name | Effect | Quantitative estimate of variation (absolute, %) |
| ------------------------- | ------ | ------------------------------------------------ |
|                           |        |                                                  |

## TCO, ROI and Break even

Define the TCO for the change (use a 3 -5 years horizon)

Estimate costs (from TCO) and savings, and discuss the number of years needed to recover the investment

## Risks

Discuss the main risks (technological, organizational, human factors) related to the change, and what can be done to reduce them

# Conclusion

In summary, why the organization should buy (and pay for) your proposal of change?