---
swagger: "2.0"
x-collection-name: Google Sheets
x-complete: 0
info:
  title: Google Sheets Get Spreadsheet
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
x-streamrank:
  polling_total_time_average: ~
  polling_size_download_average: ~
  streaming_total_time_average: ~
  streaming_size_download_average: ~
  change_yes: ~
  change_no: ~
  time_percentage: ~
  size_percentage: ~
  change_percentage: "200"
  last_run: ~
  days_run: ~
  minute_run: ~
---