---
swagger: "2.0"
x-collection-name: Google Sheets
x-complete: 0
info:
  title: Google Sheets Batch Update Spreadsheet
  description: |-
    Sets values in one or more ranges of a spreadsheet.
    The caller must specify the spreadsheet ID,
    a valueInputOption, and one or more
    DataFilterValueRanges.
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
    put:
      summary: Get Spreadsheet Values In Range
      description: |-
        Sets values in a range of a spreadsheet.
        The caller must specify the spreadsheet ID, range, and
        a valueInputOption.
      operationId: sheets.spreadsheets.values.update
      x-api-path-slug: spreadsheetsspreadsheetidvaluesrange-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: includeValuesInResponse
        description: Determines if the update response should include the valuesof
          the cells that were updated
      - in: path
        name: range
        description: The A1 notation of the values to update
      - in: query
        name: responseDateTimeRenderOption
        description: Determines how dates, times, and durations in the response should
          berendered
      - in: query
        name: responseValueRenderOption
        description: Determines how values in the response should be rendered
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
      - in: query
        name: valueInputOption
        description: How the input data should be interpreted
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values/{range}:append:
    post:
      summary: Append Values To Spreadsheet
      description: |-
        Appends values to a spreadsheet. The input range is used to search for
        existing data and find a "table" within that range. Values will be
        appended to the next row of the table, starting with the first column of
        the table. See the
        [guide](/sheets/api/guides/values#appending_values)
        and
        [sample code](/sheets/api/samples/writing#append_values)
        for specific details of how tables are detected and data is appended.

        The caller must specify the spreadsheet ID, range, and
        a valueInputOption.  The `valueInputOption` only
        controls how the input data will be added to the sheet (column-wise or
        row-wise), it does not influence what cell the data starts being written
        to.
      operationId: sheets.spreadsheets.values.append
      x-api-path-slug: spreadsheetsspreadsheetidvaluesrangeappend-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: includeValuesInResponse
        description: Determines if the update response should include the valuesof
          the cells that were appended
      - in: query
        name: insertDataOption
        description: How the input data should be inserted
      - in: path
        name: range
        description: The A1 notation of a range to search for a logical table of data
      - in: query
        name: responseDateTimeRenderOption
        description: Determines how dates, times, and durations in the response should
          berendered
      - in: query
        name: responseValueRenderOption
        description: Determines how values in the response should be rendered
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
      - in: query
        name: valueInputOption
        description: How the input data should be interpreted
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values/{range}:clear:
    post:
      summary: Clear Value From Spreadsheet
      description: |-
        Clears values from a spreadsheet.
        The caller must specify the spreadsheet ID and range.
        Only values are cleared -- all other properties of the cell (such as
        formatting, data validation, etc..) are kept.
      operationId: sheets.spreadsheets.values.clear
      x-api-path-slug: spreadsheetsspreadsheetidvaluesrangeclear-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: range
        description: The A1 notation of the values to clear
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values:batchClear:
    post:
      summary: Clear Range of Value From Spreasheet
      description: |-
        Clears one or more ranges of values from a spreadsheet.
        The caller must specify the spreadsheet ID and one or more ranges.
        Only values are cleared -- all other properties of the cell (such as
        formatting, data validation, etc..) are kept.
      operationId: sheets.spreadsheets.values.batchClear
      x-api-path-slug: spreadsheetsspreadsheetidvaluesbatchclear-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values:batchGet:
    get:
      summary: Get Value From Spreadsheet
      description: |-
        Returns one or more ranges of values from a spreadsheet.
        The caller must specify the spreadsheet ID and one or more ranges.
      operationId: sheets.spreadsheets.values.batchGet
      x-api-path-slug: spreadsheetsspreadsheetidvaluesbatchget-get
      parameters:
      - in: query
        name: dateTimeRenderOption
        description: How dates, times, and durations should be represented in the
          output
      - in: query
        name: majorDimension
        description: The major dimension that results should use
      - in: query
        name: ranges
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
  /spreadsheets/{spreadsheetId}/values:batchUpdate:
    post:
      summary: Update Values In Spreadsheet
      description: |-
        Sets values in one or more ranges of a spreadsheet.
        The caller must specify the spreadsheet ID,
        a valueInputOption, and one or more
        ValueRanges.
      operationId: sheets.spreadsheets.values.batchUpdate
      x-api-path-slug: spreadsheetsspreadsheetidvaluesbatchupdate-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}:batchUpdate:
    post:
      summary: Update Spreadsheet
      description: Spreadsheet
      operationId: sheets.spreadsheets.batchUpdate
      x-api-path-slug: spreadsheetsspreadsheetidbatchupdate-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The spreadsheet to apply the updates to
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/developerMetadata/{metadataId}:
    get:
      summary: Get Spreadsheet Metadata
      description: |-
        Returns the developer metadata with the specified ID.
        The caller must specify the spreadsheet ID and the developer metadata's
        unique metadataId.
      operationId: sheets.spreadsheets.developerMetadata.get
      x-api-path-slug: spreadsheetsspreadsheetiddevelopermetadatametadataid-get
      parameters:
      - in: path
        name: metadataId
        description: The ID of the developer metadata to retrieve
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to retrieve metadata from
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/developerMetadata:search:
    post:
      summary: Update Spreadsheet Metadata
      description: |-
        Returns all developer metadata matching the specified DataFilter.
        If the provided DataFilter represents a DeveloperMetadataLookup object,
        this will return all DeveloperMetadata entries selected by it. If the
        DataFilter represents a location in a spreadsheet, this will return all
        developer metadata associated with locations intersecting that region.
      operationId: sheets.spreadsheets.developerMetadata.search
      x-api-path-slug: spreadsheetsspreadsheetiddevelopermetadatasearch-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to retrieve metadata from
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values:batchClearByDataFilter:
    post:
      summary: Batch Update of Spreadsheet
      description: |-
        Clears one or more ranges of values from a spreadsheet.
        The caller must specify the spreadsheet ID and one or more
        DataFilters. Ranges matching any of the specified data
        filters will be cleared.  Only values are cleared -- all other properties
        of the cell (such as formatting, data validation, etc..) are kept.
      operationId: sheets.spreadsheets.values.batchClearByDataFilter
      x-api-path-slug: spreadsheetsspreadsheetidvaluesbatchclearbydatafilter-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values:batchGetByDataFilter:
    post:
      summary: Return Spreadsheet Ranges
      description: |-
        Returns one or more ranges of values that match the specified data filters.
        The caller must specify the spreadsheet ID and one or more
        DataFilters.  Ranges that match any of the data filters in
        the request will be returned.
      operationId: sheets.spreadsheets.values.batchGetByDataFilter
      x-api-path-slug: spreadsheetsspreadsheetidvaluesbatchgetbydatafilter-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to retrieve data from
      responses:
        200:
          description: OK
      tags:
      - Spreadsheet
  /spreadsheets/{spreadsheetId}/values:batchUpdateByDataFilter:
    post:
      summary: Batch Update Spreadsheet
      description: |-
        Sets values in one or more ranges of a spreadsheet.
        The caller must specify the spreadsheet ID,
        a valueInputOption, and one or more
        DataFilterValueRanges.
      operationId: sheets.spreadsheets.values.batchUpdateByDataFilter
      x-api-path-slug: spreadsheetsspreadsheetidvaluesbatchupdatebydatafilter-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: spreadsheetId
        description: The ID of the spreadsheet to update
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