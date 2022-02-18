Model of Organization � To Be



# Summary of changes

Here describe at high level the change(s), and their motivation. Link with critical points identified in As Is analysis

The following sections are meant to describe in more detail the changes, using the same structure used in the As Is document.

# Organizational variables

Keep this section and subsections, if there is no change just write &#39;no change&#39;.  In case there is a change detail it.

## Size

## Products services

## Goal, goal type, vision, mission, strategy

## Culture

## Structure

### IT office

## Formalization specialization centralization

## Organizational type

# Business model canvas

if there is no change just write &#39;no change&#39;

other wise detail only the box(es) that change



# IS Views

## Functional view, data

Ticket order now have an additional field: customer number

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
  + quantity
}

Product "+" -- "*" TicketOrder : ordered in >
Product "*" -- "*" TicketOrder : possible substitude >
Ingredient "+" -- "*" Product 
@enduml
```

## Functional view, processes

Write no change if the model remains as in As Is

### Process selection

Report the PICK chart (see process redesign chapter)  used to select the process to be changed and argument about it

### Process y

For each changed process report the new BPMN (highlight where are the changes and why) and  the software functions needed by the IS, as follows

| Activity in BPMN | Supporting Software functions |
| --- | --- |
|   |   |
|   |   |

## IT view

### Application portfolio

Write no change if the portfolio remains as in As Is

Otherwise list here the new portfolio, highlighting new applications, and abandoned applications

#### Selection

Describe the applications considered for the selection

| Application name | Vendor | Description | Price model and fees |
| --- | --- | --- | --- |
|   |   |   |   |

Describe here how the selection of the new application was made

| Criterion | Application1 | Application2 | Application x |
| --- | --- | --- | --- |
|   |   |   |   |

Alternatively argue that the new application should be developed custom for the company.

#### Coverage

Show how the selected application provides the software functions needed (as identified in Functional view, processes section), discuss gaps, if any

| Software function needed (from process view) | Software function provided by application selected | Gap analysis |
| --- | --- | --- |
|   |   |   |



### Technological view

Write no change in case. Otherwise report the new deployment diagram and highlight the changes

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
| --- | --- | --- |
|   |   |   |

## TCO, ROI and Break even

Define the TCO for the change (use a 3 -5 years horizon)

Estimate costs (from TCO) and savings, and discuss the number of years needed to recover the investment

## Risks

Discuss the main risks (technological, organizational, human factors) related to the change, and what can be done to reduce them

# Conclusion

In summary, why the organization should buy (and pay for) your proposal of change?