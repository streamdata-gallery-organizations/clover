---
swagger: "2.0"
x-collection-name: Clover
x-complete: 0
info:
  title: Clover Update a single tip suggestion
  version: 1.0.0
  description: Update a single tip suggestion.
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