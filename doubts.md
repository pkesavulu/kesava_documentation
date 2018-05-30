// if cell type is numebr then it call this method 

private Object numeric(Cell cell) {  

		if (cell.getCellStyle().getDataFormatString().contains("%")) {
			return cell.getNumericCellValue() * 100;
		} else if (HSSFDateUtil.isCellDateFormatted(cell)) {
			if (config.getFormatDate() != null) {
				return config.getFormatDate().format(cell.getDateCellValue());
			}
			return cell.getDateCellValue();
		}
		return Double.valueOf(cell.getNumericCellValue());
	}