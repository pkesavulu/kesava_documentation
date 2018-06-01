# java - excel:-
---

## apache poi package use to parse the excel sheet.

- workbook package -> "org.apache.pois.ss.usermodel.workbook"
- HSSFWorkbook package->"org.apache.poi.hsf.usermodel.HSSFWorkbook" 

# create workbook:-
---

//create workbook

1.workbook wb = new HSSFWorkbook();


// create sheet in workbook

2.Sheet sheet1 = wb.createsheet();

// create excel file using FileoutputStream

3.FileOutputStream output = new FileOutputStream("sample.txt");

// To write anything using workbook 

wb.write(output);

// finally close the work book

output.close();




# create safe sheet name:-
---

1. Sheet sheet1 = wb.createSheet();
2. Sheet sheet2 = wb.createSheet("mysheet");

> Note : If we use ? for createing sheet name in excel it won't allowed, so simple to use below syntax to create sheet name.
```    
	Syntax:- Sheet sheet3 = wb.createSheet(WorkbookUtil.createSafeSheetName("##$$?flfj?????*6755y7e8"));
```

# how to create row in excel sheet:-
---

> use this package for row: "org.apache.poi.ss.usermodel.Workbook"


 1. Row row = sheet.createRow(1);

 2. Cell cell = row.createCell(4);

 3. cell.setCellValue("Hi there")


# how to set values and create formula:-
---

    Cell cell1 = sheet.CreateRow(0).creatCell(0);
    Cell cell2 = sheet.createRow(1).createCell(1);
    Cell cell3 = sheet.createRow(2).createcell(2);
	 
    cell1.setCellValue(56);
	cell2.setCellValue(67);
	cell3.setCellFormula("A1+B1");
		or
	cell3.setCellFormula("SUM(A1:B1)");


# cell merging:-(use to merge the cell into single cell)
---

```
syntax:- sheet3.addMergedRegion(new CellRangeAddress(firstRow, lastRow, firstCol, lastCol))
```
```

example:-

Sheet sheet = workbook.createSheet("sampleSheet")

sheet.addMergedRegion(new CellRangeAddress(0,4,0,3)) 

Cell cell = sheet.createRow(0).createCell(0);

```

# how to print selected excel sheet in terminal using java.
---

- This code use to read the excel data and print into a terminal

```
import org.apache.poi.hssf.usermodel.HSSFWorkbook;
import org.apache.poi.poifs.filesystem.NPOIFSFileSystem;
import org.apache.poi.ss.usermodel.Cell;
import org.apache.poi.ss.usermodel.Row;
import org.apache.poi.ss.usermodel.Sheet;
import org.apache.poi.ss.usermodel.Workbook;

import java.util.*;
import javax.swing.*;

public class IterationCell {

	public static void main(String[] args) {

		JFileChooser jf = new JFileChooser();

		int returnvalue = jf.showOpenDialog(null);

		try {

			Workbook wb = new HSSFWorkbook(new NPOIFSFileSystem(jf.getSelectedFile()));

			Sheet sheet = wb.getSheetAt(0);

			for (Iterator<Row> itr = sheet.rowIterator(); itr.hasNext();) {

				Row row = itr.next();

				for (Iterator<Cell> itc = row.cellIterator(); itc.hasNext();) {

					Cell cell = itc.next();

					cell.setCellType(Cell.CELL_TYPE_STRING);

					System.out.print(cell.getStringCellValue() + " \t ");

				}

				System.out.println();
			}

		} catch (Exception e) {
			e.printStackTrace();
		}
	}

}

```


## use for each in this place

```
	Sheet sheet = wb.getSheetAt(0);

			for (Iterator<Row> itr = sheet.rowIterator(); itr.hasNext();) {

				Row row = itr.next();

				for (Iterator<Cell> itc = row.cellIterator(); itc.hasNext();) {

					Cell cell = itc.next();

					cell.setCellType(Cell.CELL_TYPE_STRING);

					System.out.print(cell.getStringCellValue() + " \t ");

				}

				System.out.println();
			}
```

   (or)     

```
    for(Row row : sheet){
		for(Cell cell:row){

			cell.setCellType(Cell.CELL_TYPE_STRING);

					System.out.print(cell.getStringCellValue() + " \t ");

		}

			System.out.println();
	}
```

