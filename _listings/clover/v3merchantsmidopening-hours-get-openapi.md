---
swagger: "2.0"
x-collection-name: Clover
x-complete: 0
info:
  title: Clover Get a list this merchant opening hours
  version: 1.0.0
  description: Get a list this merchant opening hours.
host: /merchants
basePath: https://api.clover.com
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v3/merchants/{mId}:
    get:
      summary: Get a single merchant
      description: Get a single merchant.
      operationId: GetMerchant
      x-api-path-slug: v3merchantsmid-get
      parameters:
      - in: query
        name: expand
        description: 'Expandable fields: [employees, bankProcessing, externalMerchant,
          merchantBoarding, deviceBoarding, programExpress, hierarchy, shifts, orders,
          address, logos, owner, items, tags, tenders, payments, gateway, printers,
          modifierGroups, properties, tipSuggestions, openingHours, partnerApp, selfBoardingApplication]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - MId
    post:
      summary: Update a merchant
      description: Update a merchant.
      operationId: UpdateMerchant
      x-api-path-slug: v3merchantsmid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: expand
        description: 'Expandable fields: [employees, bankProcessing, externalMerchant,
          merchantBoarding, deviceBoarding, programExpress, hierarchy, shifts, orders,
          address, logos, owner, items, tags, tenders, payments, gateway, printers,
          modifierGroups, properties, tipSuggestions, openingHours, partnerApp, selfBoardingApplication]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - MId
  /v3/merchants/{mId}/address:
    get:
      summary: Get a merchant's address
      description: Get a merchant's address.
      operationId: GetMerchantAddress
      x-api-path-slug: v3merchantsmidaddress-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Address
  /v3/merchants/{mId}/gateway:
    get:
      summary: Get a merchant's payment gateway configuration
      description: Get a merchant's payment gateway configuration.
      operationId: GetMerchantGateway
      x-api-path-slug: v3merchantsmidgateway-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Gateway
  /v3/merchants/{mId}/properties:
    get:
      summary: Get a merchant's properties
      description: Get a merchant's properties.
      operationId: GetMerchantProperties
      x-api-path-slug: v3merchantsmidproperties-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Properties
    post:
      summary: Update merchant properties
      description: Update merchant properties.
      operationId: UpdateMerchantProperties
      x-api-path-slug: v3merchantsmidproperties-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Properties
  /v3/merchants/{mId}/default_service_charge:
    get:
      summary: Get default service charge for a merchant
      description: The Merchant's default service charge, set via the Setup App (https://www.clover.com/setupapp).
      operationId: GetDefaultServiceCharge
      x-api-path-slug: v3merchantsmiddefault-service-charge-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Default
      - Service
      - Charge
  /v3/merchants/{mId}/sync/{table}:
    get:
      summary: Get a sync token (deprecated)
      description: Get a sync token (deprecated).
      operationId: GetSyncToken
      x-api-path-slug: v3merchantsmidsynctable-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: table
        description: Table Name
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Sync
      - Table
  /v3/merchants/{mId}/tip_suggestions:
    get:
      summary: Get all tip suggestions for a merchant
      description: Get all tip suggestions for a merchant.
      operationId: GetTipSuggestions
      x-api-path-slug: v3merchantsmidtip-suggestions-get
      parameters:
      - in: query
        name: filter
        description: 'Filter fields: [id, name, percentage, enabled]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tip
      - Suggestions
  /v3/merchants/{mId}/tip_suggestions/{tId}:
    get:
      summary: Get a single tip suggestion
      description: Get a single tip suggestion.
      operationId: GetTipSuggestion
      x-api-path-slug: v3merchantsmidtip-suggestionstid-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: tId
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tip
      - Suggestions
      - TId
    post:
      summary: Update a single tip suggestion
      description: Update a single tip suggestion.
      operationId: UpdateTipSuggestion
      x-api-path-slug: v3merchantsmidtip-suggestionstid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: tId
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tip
      - Suggestions
      - TId
  /v3/merchants/{mId}/order_types:
    get:
      summary: Get all order types for a merchant
      description: Merchants have the ability to create custom order types via the
        Setup App (https://www.clover.com/setupapp). These custom order types can
        be associated with a System Order Type (see /v3/merchants/{mId}/system_order_types).
        Custom Order Types can support items in all categories (filterCategories=false)
        or a subset of the merchant's categories (filterCategories=true and categories
        property contains the list of supported categories). Note that when expanding
        the categories for an order type, they will only be returned if this orderType
        only supports a subset of the categories (filterCategories=true). If the orderType
        supports all categories (filterCategories=false) then you should make a GET
        request to /v3/merchants/{mId}/categories.
      operationId: GetOrderTypes
      x-api-path-slug: v3merchantsmidorder-types-get
      parameters:
      - in: query
        name: expand
        description: 'Expandable fields: [hours, attributes, categories]'
      - in: query
        name: filter
        description: 'Filter fields: [id, deletedTime]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Order
      - Types
    post:
      summary: Create Order Type For Merchant
      description: Create order type for merchant.
      operationId: CreateOrderType
      x-api-path-slug: v3merchantsmidorder-types-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: expand
        description: 'Expandable fields: [hours, attributes, categories]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Order
      - Types
  /v3/merchants/{mId}/order_types/{orderTypeId}:
    get:
      summary: Get a single order type
      description: Get a single order type.
      operationId: GetOrderType
      x-api-path-slug: v3merchantsmidorder-typesordertypeid-get
      parameters:
      - in: query
        name: expand
        description: 'Expandable fields: [hours, attributes, categories]'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: orderTypeId
        description: Order Type Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Order
      - Types
      - OrderTypeId
    post:
      summary: Update a single order type
      description: Update a single order type.
      operationId: UpdateOrderType
      x-api-path-slug: v3merchantsmidorder-typesordertypeid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: expand
        description: 'Expandable fields: [hours, attributes, categories]'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: orderTypeId
        description: Order Type Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Order
      - Types
      - OrderTypeId
    delete:
      summary: Delete an order type
      description: Delete an order type.
      operationId: DeleteOrderType
      x-api-path-slug: v3merchantsmidorder-typesordertypeid-delete
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: orderTypeId
        description: Order Type Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Order
      - Types
      - OrderTypeId
  /v3/merchants/{mId}/order_type_categories:
    post:
      summary: Create or delete a order type category
      description: Create or delete a order type category.
      operationId: CreateOrDeleteOrderTypeCategories
      x-api-path-slug: v3merchantsmidorder-type-categories-post
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Order
      - Type
      - Categories
  /v3/merchants/{mId}/system_order_types:
    get:
      summary: Return a list of system order types
      description: Merchants can create custom Order Types via "/v3/merchants/{mId}/order_types".
        It is useful to associate these custom order types with particular system
        order types in order to group things functionally. For example, a merchant
        may have a "Lunch Take-Out" order type and a "Dinner Take-Out" order type.
        These two order types can be associated with the "TAKE-OUT-TYPE" system order
        type so that applications can understand that they are both take-out order
        types.
      operationId: GetSystemOrderTypes
      x-api-path-slug: v3merchantsmidsystem-order-types-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - System
      - Order
      - Types
  /v3/merchants/{mId}/roles:
    get:
      summary: Get all roles from a merchant
      description: Get all roles from a merchant.
      operationId: GetRoles
      x-api-path-slug: v3merchantsmidroles-get
      parameters:
      - in: query
        name: expand
        description: 'Expandable fields: [employees]'
      - in: query
        name: filter
        description: 'Filter fields: [modifiedTime, systemRole, name, id, deletedTime]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Roles
    post:
      summary: Create a role
      description: Create a role.
      operationId: CreateRole
      x-api-path-slug: v3merchantsmidroles-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Roles
  /v3/merchants/{mId}/roles/{rId}:
    get:
      summary: Get a single role
      description: Get a single role.
      operationId: GetRole
      x-api-path-slug: v3merchantsmidrolesrid-get
      parameters:
      - in: query
        name: expand
        description: 'Expandable fields: [employees]'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: rId
        description: Role Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Roles
      - RId
    post:
      summary: Update a single role
      description: Update a single role.
      operationId: UpdateRole
      x-api-path-slug: v3merchantsmidrolesrid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: expand
        description: 'Expandable fields: [employees]'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: rId
        description: Role Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Roles
      - RId
    delete:
      summary: Delete a role
      description: Delete a role.
      operationId: DeleteRole
      x-api-path-slug: v3merchantsmidrolesrid-delete
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: rId
        description: Role Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Roles
      - RId
  /v3/merchants/{mId}/tenders:
    get:
      summary: Get all tenders for a merchant
      description: Get all tenders for a merchant.
      operationId: GetMerchantTenders
      x-api-path-slug: v3merchantsmidtenders-get
      parameters:
      - in: query
        name: filter
        description: 'Filter fields: [labelKey, label, opensCashDrawer, enabled, visible,
          instruction, id, merchantId, systemTenderId, deletedTime, modifiedTime]'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tenders
    post:
      summary: Adds a new tender
      description: Returns an object representing newly added merchant tender, with
        a generated ID.
      operationId: CreateMerchantTender
      x-api-path-slug: v3merchantsmidtenders-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tenders
  /v3/merchants/{mId}/tenders/{tenderId}:
    get:
      summary: Get a single merchant tender
      description: Get a single merchant tender.
      operationId: GetMerchantTender
      x-api-path-slug: v3merchantsmidtenderstenderid-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: tenderId
        description: Tender Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tenders
      - TenderId
    post:
      summary: Updates an existing tender
      description: Returns an object representing updated merchant tender.
      operationId: UpdateMerchantTender
      x-api-path-slug: v3merchantsmidtenderstenderid-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: tenderId
        description: Tender Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tenders
      - TenderId
    delete:
      summary: Deletes an existing tender
      description: Deletes an existing tender.
      operationId: DeleteMerchantTender
      x-api-path-slug: v3merchantsmidtenderstenderid-delete
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      - in: path
        name: tenderId
        description: Tender Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Tenders
      - TenderId
  /v3/merchants/{mId}/opening_hours:
    get:
      summary: Get a list this merchant opening hours
      description: Get a list this merchant opening hours.
      operationId: GetAllMerchantOpeningHours
      x-api-path-slug: v3merchantsmidopening-hours-get
      parameters:
      - in: path
        name: mId
        description: Merchant Id
      responses:
        200:
          description: OK
      tags:
      - Merchants
      - Opening
      - Hours
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---