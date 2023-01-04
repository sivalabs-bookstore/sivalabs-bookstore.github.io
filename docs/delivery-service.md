# Delivery Service
The delivery-service manages order delivery process.

## Event Handlers
1. ORDER_CREATED event handler: 
   * Save order details with status="READY_TO_SHIP"

## Jobs:
### OrderDeliveryJob:
* Starts processing orders with status="READY_TO_SHIP"
* deliver the order (after certain delay) and publish ORDER_DELIVERED event.
* If the order can't be delivered then publish ORDER_CANCELLED event.
* In case of any failures publish ORDER_ERROR event.
