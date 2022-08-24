package excelutility;

import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;

public class excelutility {
	
	static String projectPath;
	static XSSFWorkbook workbook;
	static XSSFSheet sheet;
	
	
	public excelutility(String excelPath , String sheetName) {
		try {
		 //projectPath = System.getProperty("name.dir");
         workbook = new XSSFWorkbook(excelPath);
         sheet = workbook.getSheet(sheetName);
	}catch(Exception e) {
		e.printStackTrace();
	}
	}
	
	public static void main(String[] args) {
		getRowCount();
		getCellDataString(0,0);
		getCellDataNumber(1,1);
	}

	public static void getRowCount() {
		try {
			int rowCount = sheet.getPhysicalNumberOfRows();
			System.out.println("No of rows : "+rowCount);
		}catch(Exception exp) {
			System.out.println(exp.getMessage());
			System.out.println(exp.getCause());
			exp.printStackTrace();
		}
			
	}	
			
			
			
			
		/* projectPath = System.getProperty("name.dir");
		 workbook = new XSSFWorkbook(projectPath+"/excel/data.xlsx");
         try {
			sheet = workbook.getSheet("Sheet1");
		} catch (Exception e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
  int rowCount = sheet.getPhysicalNumberOfRows();
  System.out.println("No of rows :" +rowCount);
  
	}catch(Exception exp) {
		System.out.println(exp.getMessage());
		System.out.println(exp.getCause());
		exp.printStackTrace();*/
		


	public static void getCellDataString(int rowNum , int colNum){
		try {
			 /*projectPath = System.getProperty("name.dir");
	         workbook = new XSSFWorkbook(projectPath+"/excel/data.xlsx");
	         sheet = workbook.getSheet("Sheet1"); */
	       String cellData =  sheet.getRow(rowNum).getCell(colNum).getStringCellValue();
	       System.out.println(cellData);
	       
	}catch(Exception exp) {
		System.out.println(exp.getMessage());
		System.out.println(exp.getCause());
		exp.printStackTrace();
		
	}
	}

	public static void getCellDataNumber(int rowNum , int colNum){
		try {
			/* projectPath = System.getProperty("name.dir");
	         workbook = new XSSFWorkbook(projectPath+"/excel/data.xlsx");
	         sheet = workbook.getSheet("Sheet1"); */
	       double cellData =  sheet.getRow(rowNum).getCell(colNum).getNumericCellValue();
	       System.out.println(cellData);
	       
	}catch(Exception exp) {
		System.out.println(exp.getMessage());
		System.out.println(exp.getCause());
		exp.printStackTrace();
		
}
	}
}