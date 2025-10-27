import pandas as pd
from pypdf import PdfReader
import pdfplumber

pdf = pdfplumber.open("C:\Users\katie\Downloads\2024_IC3Report.pdf")
p28 = pdf.pages[28]
causes_table = p28.extract_table()
causes_table[:3]

reader = PDfReader("C:\Users\katie\Downloads\2024_IC3Report.pdf")
page28 = reader.pages[28]
