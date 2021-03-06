# Course Materials Cost Estimator

## Contents

- [Objective](#objective)
- [Cost Estimation](#cost-estimation)
- [Deltas](#deltas)
- [Instructions for Use](#instructions-for-use)
- [HEOA Spreadsheet](#heoa-spreadsheet)
- [Notes](#notes)

## Objective

The objective of this tool is to efficiently estimate the cost of ownership for new materials required for all sections of all courses.

_This tool is focused on identifying classes with no or low cost materials, use care for other purposes._

## Cost Estimation

- The tool reads an HEOA spreadsheet and totals the **cost of ownership for new materials**, per section, for all courses
- Materials may be textbooks, digital media, or any other supporting item
- The _highest_ cost of any given material is used. For example, if there are three options for the same book, the most expensive is used in case that is the only item available.
- The tool tries to identify duplicate items. If there are two books, _The Instruction Book_ and _Instruction Book_, the tool will consider them the same because the important words in the title are _Instruction_ and _Book_. _Instruction Book_ and _Book Instruction_ are presumed to be different because the words are in a different order.
- The accuracy of the estimation will vary based on the materials - items such as clothing where multiple sizes are listed may not be accurately calculated.
- Items with the word _subscription_ in the title will not be included in estimates because the student does not own them
- eBooks listed as _Web_ are assumed to be _subscriptions_ and are not included, unless no other materials are specified
- Materials listed as _Downloadable_ are included as ownership is implied
- Include a disclaimer with the results, for example: _Be sure to check the bookstore site, and consult with the instructor for the class prior to registration._

## Deltas

The estimator includes a local store delta check.

Each time the cost of materials is estimated, the costs are stored locally. The next time the tool runs, it will add the text _changed_ to any class that has been added or has a different cost of materials.

If a class has been removed from the HEOA file, its absence will not be noted.

## Instructions For Use

### HEOA Spreadsheet

Contact your bookstore manager to get the HEOA spreadsheet, or FTP credentials.

- If you have an HEOA spreadsheet, upload the file
- If you have FTP credentials for the HEOA feed, enter them and click _Go_
- A preview of the spreadsheet is displayed, whether you uploaded it or got it from the feed. The preview allows you to quickly check whether the file you're working with is the one you expected, it shows every row of data, but not every cell in the row.

### Downloading the estimated cost of materials

The **Download** button will deliver a spreadsheet with the estimated cost of materials for all sections in the HEOA file. You may open it or download it.

## Cost Estimation Spreadsheet

The cost estimation spreadsheet includes all the classes in the HEOA spreadsheet. Use the CRN number for class identification.

There is no evaluation mechanism in the spreadsheet. The data may be analyzed any way.

### Filtering

The spreadsheet can be filtered to make it easier to see which sections have changed since the last time the spreadsheet was created.

1. Click on the Data tab and select column I  
   ![Click on the Data tab and select column I](public/assets/doc-images/excel-filter-hints-1.png)
1. Click on Filter  
   ![Click on Filter](public/assets/doc-images/excel-filter-hints-2.png)
1. Set the filter to only display rows with the value _changed_ in column I  
   ![Click on Filter](public/assets/doc-images/excel-filter-hints-3.png)

### Highlighting

You may use Conditional Formatting to highlight rows in the spreadsheet. These instructions describe how to emphasize the courses with an estimated material cost of less than \$40.

1. Select column D  
   ![Select column D](public/assets/doc-images/excel-highlight-hints-1.png)
1. Click on _Conditional Formatting_  
   ![Click Conditional Formatting](public/assets/doc-images/excel-highlight-hints-2.png)
1. Choose how you would like to highlight the estimated cost of materials  
   ![Choose Conditional Formatting](public/assets/doc-images/excel-highlight-hints-3.png)
1. Example display  
   ![Example display](public/assets/doc-images/excel-highlight-hints-4.png)

The spreadsheet can not be styled or customized further without a paid license. Ref: <https://gist.github.com/SheetJSDev/24b8acd317d01999d721b38de7c53021>

### Notes

Notes in the HEOA file are included in the output, they may be preceded by additional notes as follows:

1. _No materials_ - no materials are listed for the section, which implies the cost of materials is zero
1. _\*\*\* One or more of the materials is a CHOICE \*\*\*_ - the total cost of materials will not exceed the value shown, but it is likely less.

### Credits

- <https://github.com/bencodezen/vue-enterprise-boilerplate>
- <https://github.com/SheetJS/sheetjs>
- <https://vue-xlsx.netlify.app/>

### Source

- <https://github.com/bgamrat/nolo>

#### Development Workflow

clone/download

```sh
yarn install
yarn dev --open
```

**_Update_** `deploy.sh` before use
