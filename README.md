# Data restful endpoints

## Introduction

ATUM has provided access to certain data regarding items/orders/shipments.  We'll be going over those endpoints and how to use them.  ReferenceId and Order are interchangable and mean the same thing.

## Item based endpoints

### /reports/all-ordered-items.csv
Get all information about ordered items

- Request method
  - get
- Output
  - csv

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|

### /reports/item-status/{itemIds}
Get the item status based upon itemIds passed in.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|
|itemIds|Integer[]|Yes|Item ids in order|
|include|String[]|No|Options that will trigger more information to be present</br><ul><li>shippingContainers</li><li>designInfo</li><li>clonedSequence</li><li>clonedSequenceLength</li><li>requestVectorName</li><li>shippedVectorName</li></ul>|


### /order-items/{refId}
Get all items in this order defined by refId

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|
|refId|Integer|Yes|ReferenceId aka OrderId|

### /item/downloadAllFiles/{itemId}
Download ALL files for an item.  Can be from shipment and design process.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|
|itemId|Integer|Yes|itemId provided when placing order|

## Order based endpoints

### /open-orders
Get all orders that haven’t been shipped or canceled yet.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|

### /orders/downloadFiles/{refId}/{shipmentNumber}
Download files associated with shipment

- Request method
  - get
- Output
  - zip

Parameters
|Name|Type|Required|Description|
|----|----|-----------|
|refId|Integer|Yes|ReferenceId aka OrderId|
|shipmentNumber|Integer|Yes|Shipment number provided when we ship the order.  There can be multiple shipments for a an order.|

### /orders/downloadAllFiles/{refId}
Download ALL files for an order regardless of shipment

- Request method
  - get
- Output
  - zip

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|
|refId|Integer|Yes|ReferenceId aka OrderId|

### /reports/gene-info/order/{referenceId}
Get gene information for order placed

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|
|referenceId|Integer|Yes|ReferenceId aka OrderId|


## Vector based endpoints

### /inhouse-vectors
Get all inhouse vector information.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|

### /account/custom-vectors
Get all customs vectors for this account(not just contact).

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|

## Account based endpoints

### /account/addresses
Get all billing and shipping addresses in address book.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|

### /account/payment-methods
Get all payment methods in account(not not just contact)

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Required|Description|
|----|----|--------|-----------|
