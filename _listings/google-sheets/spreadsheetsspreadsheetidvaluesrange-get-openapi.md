---
swagger: "2.0"
x-collection-name: Google Sheets
x-complete: 0
info:
  title: Google Sheets Get Spreadsheet Values
  description: |-
    Returns a range of values from a spreadsheet.
    The caller must specify the spreadsheet ID and a range.
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
  /spreadsheets/{spreadsheetId}:
    get:
      summary: Get Spreadsheet
      description: |-
        Returns the spreadsheet at the given ID.
        The caller must specify the spreadsheet ID.

        By default, data within grids will not be returned.
        You can include grid data one of two ways:

        * Specify a field mask listing your desired fields using the `fields` URL
        parameter in HTTP

        * Set the includeGridData
        URL parameter to true.  If a field mask is set, the `includeGridData`
        parameter is ignored

        For large spreadsheets, it is recommended to retrieve only the specific
        fields of the spreadsheet that you want.

        To retrieve only subsets of the spreadsheet, use the
        ranges URL parameter.
        Multiple ranges can be specified.  Limiting the range will
        return only the portions of the spreadsheet that intersect the requested
        ranges. Ranges are specified using A1 notation.
      operationId: sheets.spreadsheets.get
      x-api-path-slug: spreadsheetsspreadsheetid-get
      parameters:
      - in: query
        name: includeGridData
        description: True if grid data should be returned
      - in: query
        name: ranges
        description: The ranges to retrieve from the spreadsheet
      - in: path
        name: spreadsheetId
        description: The spreadsheet to request
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/sheets/{sheetId}:copyTo:
    post:
      summary: Copy Spreadsheet
      description: |-
        Copies a single sheet from a spreadsheet to another spreadsheet.
        Returns the properties of the newly created sheet.
      operationId: sheets.spreadsheets.sheets.copyTo
      x-api-path-slug: spreadsheetsspreadsheetidsheetssheetidcopyto-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: sheetId
        description: The ID of the sheet to copy
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet containing the sheet to copy
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values/{range}:
    get:
      summary: Get Spreadsheet Values
      description: |-
        Returns a range of values from a spreadsheet.
        The caller must specify the spreadsheet ID and a range.
      operationId: sheets.spreadsheets.values.get
      x-api-path-slug: spreadsheetsspreadsheetidvaluesrange-get
      parameters:
      - in: query
        name: dateTimeRenderOption
        description: How dates, times, and durations should be represented in the
          output
      - in: query
        name: majorDimension
        description: The major dimension that results should use
      - in: path
        name: range
        description: The A1 notation of the values to retrieve
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to retrieve data from
      - in: query
        name: valueRenderOption
        description: How values should be represented in the output
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