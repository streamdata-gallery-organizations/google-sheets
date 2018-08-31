---
swagger: "2.0"
x-collection-name: Google Sheets
x-complete: 0
info:
  title: Google Sheets Create Spreadsheet
  description: Creates a spreadsheet, returning the newly created spreadsheet.
  termsOfService: https://developers.google.com/terms/
  contact:
    name: Google
    url: https://google.com
  version: v4
host: sheets.googleapis.com
basePath: v4/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /spreadsheets:
    post:
      summary: Create Spreadsheet
      description: Creates a spreadsheet, returning the newly created spreadsheet.
      operationId: sheets.spreadsheets.create
      x-api-path-slug: spreadsheets-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
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