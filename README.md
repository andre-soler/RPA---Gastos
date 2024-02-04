# RPA---Gastos
Projeto focado em RPA, automatizando processos utilizando a biblioteca openpyxl (biblioteca do python). Fazendo com que o robô criado monte uma tabela no Excel a partir dos dados informados 
from openpyxl import Workbook
print("Iniciando nosso robô...")
print("Lendo dados do nosso arquivo de textos...")
file_txt = open("gastos.txt", "r", encoding="utf-8")

#ler do arquivo
arquivo = file_txt.read()

lista_dados = arquivo.splitlines()

for i in range(0,len(lista_dados)):
  lista_dados[i] = lista_dados[i].split(",")

  #criando Arquivo Excel
print("Criando Arquivo Excel")
wb = Workbook()
ws = wb.active

for row in lista_dados:
  ws.append(row)

wb.save("gastos.xlsx")
