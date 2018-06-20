---
name: Google Sheets
x-slug: google-sheets
description: 'Google Sheets is an online spreadsheet app that lets users create and
  format spreadsheets and simultaneously work with other people. Google Sheets isn&rsquo;t
  only for consumers: its used every day by businesses and schools to manage spreadsheet
  data. With the new Sheets API v4 and Sheets add-ons, that data can be accessed by
  code as well as users.'
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
x-kinRank: "9"
x-alexaRank: "0"
tags: Google Sheets
created: "2018-06-20"
modified: "2018-06-20"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/apis.md
specificationVersion: "0.14"
apis:
- name: Google Sheets Create Spreadsheet
  x-api-slug: google-sheets
  description: Creates a spreadsheet, returning the newly created spreadsheet.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheets-post-openapi.md
- name: Google Sheets Get Spreadsheet
  x-api-slug: google-sheets
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetid-get-openapi.md
- name: Google Sheets Copy Spreadsheet
  x-api-slug: google-sheets
  description: |-
    Copies a single sheet from a spreadsheet to another spreadsheet.
    Returns the properties of the newly created sheet.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/sheets/{sheetId}:copyTo
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidsheetssheetidcopyto-post-openapi.md
- name: Google Sheets Get Spreadsheet Values
  x-api-slug: google-sheets
  description: |-
    Returns a range of values from a spreadsheet.
    The caller must specify the spreadsheet ID and a range.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values/{range}
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesrange-get-openapi.md
- name: Google Sheets Get Spreadsheet Values In Range
  x-api-slug: google-sheets
  description: |-
    Sets values in a range of a spreadsheet.
    The caller must specify the spreadsheet ID, range, and
    a valueInputOption.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values/{range}
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesrange-put-openapi.md
- name: Google Sheets Append Values To Spreadsheet
  x-api-slug: google-sheets
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values/{range}:append
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesrangeappend-post-openapi.md
- name: Google Sheets Clear Value From Spreadsheet
  x-api-slug: google-sheets
  description: |-
    Clears values from a spreadsheet.
    The caller must specify the spreadsheet ID and range.
    Only values are cleared -- all other properties of the cell (such as
    formatting, data validation, etc..) are kept.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values/{range}:clear
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesrangeclear-post-openapi.md
- name: Google Sheets Clear Range of Value From Spreasheet
  x-api-slug: google-sheets
  description: |-
    Clears one or more ranges of values from a spreadsheet.
    The caller must specify the spreadsheet ID and one or more ranges.
    Only values are cleared -- all other properties of the cell (such as
    formatting, data validation, etc..) are kept.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values:batchClear
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesbatchclear-post-openapi.md
- name: Google Sheets Get Value From Spreadsheet
  x-api-slug: google-sheets
  description: |-
    Returns one or more ranges of values from a spreadsheet.
    The caller must specify the spreadsheet ID and one or more ranges.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values:batchGet
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesbatchget-get-openapi.md
- name: Google Sheets Update Values In Spreadsheet
  x-api-slug: google-sheets
  description: |-
    Sets values in one or more ranges of a spreadsheet.
    The caller must specify the spreadsheet ID,
    a valueInputOption, and one or more
    ValueRanges.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values:batchUpdate
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesbatchupdate-post-openapi.md
- name: Google Sheets Update Spreadsheet
  x-api-slug: google-sheets
  description: Spreadsheet
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}:batchUpdate
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidbatchupdate-post-openapi.md
- name: Google Sheets Get Spreadsheet Metadata
  x-api-slug: google-sheets
  description: |-
    Returns the developer metadata with the specified ID.
    The caller must specify the spreadsheet ID and the developer metadata's
    unique metadataId.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/developerMetadata/{metadataId}
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetiddevelopermetadatametadataid-get-openapi.md
- name: Google Sheets Update Spreadsheet Metadata
  x-api-slug: google-sheets
  description: |-
    Returns all developer metadata matching the specified DataFilter.
    If the provided DataFilter represents a DeveloperMetadataLookup object,
    this will return all DeveloperMetadata entries selected by it. If the
    DataFilter represents a location in a spreadsheet, this will return all
    developer metadata associated with locations intersecting that region.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/developerMetadata:search
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetiddevelopermetadatasearch-post-openapi.md
- name: Google Sheets Batch Update of Spreadsheet
  x-api-slug: google-sheets
  description: |-
    Clears one or more ranges of values from a spreadsheet.
    The caller must specify the spreadsheet ID and one or more
    DataFilters. Ranges matching any of the specified data
    filters will be cleared.  Only values are cleared -- all other properties
    of the cell (such as formatting, data validation, etc..) are kept.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values:batchClearByDataFilter
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesbatchclearbydatafilter-post-openapi.md
- name: Google Sheets Return Spreadsheet Ranges
  x-api-slug: google-sheets
  description: |-
    Returns one or more ranges of values that match the specified data filters.
    The caller must specify the spreadsheet ID and one or more
    DataFilters.  Ranges that match any of the data filters in
    the request will be returned.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values:batchGetByDataFilter
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesbatchgetbydatafilter-post-openapi.md
- name: Google Sheets Batch Update Spreadsheet
  x-api-slug: google-sheets
  description: |-
    Sets values in one or more ranges of a spreadsheet.
    The caller must specify the spreadsheet ID,
    a valueInputOption, and one or more
    DataFilterValueRanges.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}/values:batchUpdateByDataFilter
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidvaluesbatchupdatebydatafilter-post-openapi.md
- name: Google Sheets Update Spreadsheets
  x-api-slug: google-sheets
  description: |-
    Returns the spreadsheet at the given ID.
    The caller must specify the spreadsheet ID.

    This method differs from GetSpreadsheet in that it allows selecting
    which subsets of spreadsheet data to return by specifying a
    dataFilters parameter.
    Multiple DataFilters can be specified.  Specifying one or
    more data filters will return the portions of the spreadsheet that
    intersect ranges matched by any of the filters.

    By default, data within grids will not be returned.
    You can include grid data one of two ways:

    * Specify a field mask listing your desired fields using the `fields` URL
    parameter in HTTP

    * Set the includeGridData
    parameter to true.  If a field mask is set, the `includeGridData`
    parameter is ignored

    For large spreadsheets, it is recommended to retrieve only the specific
    fields of the spreadsheet that you want.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4///spreadsheets/{spreadsheetId}:getByDataFilter
  tags: Spreadsheet
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/spreadsheetsspreadsheetidgetbydatafilter-post-openapi.md
- name: Google Sheets
  x-api-slug: google-sheets
  description: 'Google Sheets is an online spreadsheet app that lets users create
    and format spreadsheets and simultaneously work with other people. Google Sheets
    isn&rsquo;t only for consumers: its used every day by businesses and schools to
    manage spreadsheet data. With the new Sheets API v4 and Sheets add-ons, that data
    can be accessed by code as well as users.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-sheets-icon.png
  humanURL: https://developers.google.com/sheets/
  baseURL: https://sheets.googleapis.com/v4/
  tags: Google Sheets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-sheets/master/_listings/google-sheets/openapi.md
x-common:
- type: x-documentation
  url: https://developers.google.com/sheets/api/
- type: x-guides
  url: https://developers.google.com/sheets/api/guides/concepts
- type: x-issues
  url: https://code.google.com/a/google.com/p/apps-api-issues/
- type: x-rate-limits
  url: https://developers.google.com/sheets/api/limits
- type: x-samples
  url: https://developers.google.com/sheets/api/samples/
- type: x-support
  url: https://developers.google.com/sheets/api/support
- type: x-website
  url: https://developers.google.com/sheets/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---