---
layout: default
title: Data Filling
parent: Korolev
---

# External Sources

## APIs

### Response Type: *CSV*
Currently only lectures API has an API of response type CSV located in the google drive folder (Contact CoCo) at `/Lectures/dynamic/Korolev-Lectures-Api.sheets`

Be careful with the spreadsheet it is the equivalent of a live database. No Credencials are needed, for safety reasons set the Sheet to Editable only for fixed Email addresses, preferably webmaster, lectures head and president everyone else can view only

`fetch` call for sheet should should be made after converting from btoa i.e `fetch(atob(BASE64_LINK))`, nowhere should the link be visible in plain text it should be obscured to Base64 at the very minimum. More sophisticated algorithms are better

#### Functions (Columns)
featured: (*Boolean*) - When set (`true/1`) will show the current row on the main site \
date: (*date, String*) - Set as `DD MMM 'YY`, Ex. *22 Apr '21, 03 Nov '22, 28 Feb '20* \
time: (*time, String*) - Set as `TTTT IST`, Ex. *1900 IST, 2200 PDT, 0300 EST*, Prefer IST \
title: (*String*) - Set as needed \
prof: (*String*) - Set as needed \
suject: (*String*) - Set as needed \
image: (*URI*) - Set Publicly hosted image URL. Image should be square and of size between 512x512 & 2048x2048. Preferably Imgur \
url: (*URI*) - Set URL for video where lecture is/will be located, Preferably: Youtube \
text: (*String*) - Description, Set as needed

#### Setting Guidelines
- DO NOT UNDER ANY CONDITION COPY PASTE INTO CELLS. Manually type in every needed piece of text, or else first paste it into vanilla notepad and then copy paste from there to strip off any invisible characters and styles
- Do not include `,` comma character, in case needed insert an `&&`, the main website compiler will replace all `&&` with `,`, the response is of CSV type so a comma will cause the columns to split unpredictably