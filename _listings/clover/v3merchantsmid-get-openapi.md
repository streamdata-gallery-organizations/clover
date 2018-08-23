---
swagger: "2.0"
x-collection-name: Clover
x-complete: 0
info:
  title: Clover Get a single merchant
  version: 1.0.0
  description: Get a single merchant.
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