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
|Name|Type|Description|
|----|----|-----------|

### /reports/item-status/{itemIds}
Get the item status based upon itemIds passed in.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Description|
|----|----|-----------|
|itemIds|Integer[]|Item ids in order
|include|String[]|Options that will trigger more information to be present</br><ul><li>shippingContainers</li><li>designInfo</li><li>clonedSequence</li><li>clonedSequenceLength</li><li>requestVectorName</li><li>shippedVectorName</li></ul>|


### /order-items/{refId}
Get all items in this order defined by refId

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Description|
|----|----|-----------|
|refId|Integer|ReferenceId aka OrderId|

## Order based endpoints

### /open-orders
Get all orders that haven’t been shipped or canceled yet.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Description|
|----|----|-----------|

## Vector based endpoints

### /inhouse-vectors
Get all inhouse vector information.

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Description|
|----|----|-----------|

### /account/custom-vectors
Get all customs vectors for this account(not just contact).

- Request method
  - get
- Output
  - json

Parameters
|Name|Type|Description|
|----|----|-----------|

## Account based endpoints
