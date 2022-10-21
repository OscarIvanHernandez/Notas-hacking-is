# PicoCTF2022 Forensic
## Objetivo
This [report](https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Pistas
How can you be sure of the redaction?
## Solucion



┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2022/RedactionGoneWrong]
└──╼ $sudo apt install poppler-utils

┌─[✗]─[oscar@oscar-parrot]─[~/forensic/2022/RedactionGoneWrong]
└──╼ $man pdftotext 
...
┌─[oscar@oscar-parrot]─[~/forensic/2022/RedactionGoneWrong]
└──╼ $pdftotext Financial_Report_for_ABC_Labs.pdf text.txt
┌─[oscar@oscar-parrot]─[~/forensic/2022/RedactionGoneWrong]
└──╼ $ls
Financial_Report_for_ABC_Labs.pdf  _Financial_Report_for_ABC_Labs.pdf.extracted  text.txt
┌─[oscar@oscar-parrot]─[~/forensic/2022/RedactionGoneWrong]
└──╼ $cat text.txt 
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.

Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.

┌─[oscar@oscar-parrot]─[~/forensic/2022/RedactionGoneWrong]
└──╼ $



## Notas adicionales
pdftotext - Portable Document Format (PDF) to text converter (version 3.03)

pdftotext puede servir para convertir a texto un pdf

## Referencias
https://www.youtube.com/watch?v=Zr0ypi_OZkA
