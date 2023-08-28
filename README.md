# Projeto-grafico-Python
Desafio proposto: Analisar e extrair dados relevantes e construir um grafico.png e um pdf 

![code](https://github.com/Lipesti/Projeto-grafico-Python/assets/88855179/16aa319b-0ddc-4e4c-b4ea-5d7f4c2f9827)

![grafico](https://github.com/Lipesti/Projeto-grafico-Python/assets/88855179/b5342ced-115c-4918-9a3f-d3fb22eb7c54)

[grafico3 (4).pdf](https://github.com/Lipesti/Projeto-grafico-Python/files/12458225/grafico3.4.pdf)


<hr>

import matplotlib.pyplot as plt
from reportlab.pdfgen import canvas


dados = {
    'Idade': [4, 36, 25, 62, 3],
    'Raça': ['Preta', 'Ignorado', 'Indígena', 'Branca', 'Ignorado']
}


plt.bar(dados['Raça'], dados['Idade'])
plt.xlabel('Raça')
plt.ylabel('Idade')
plt.title('Idade por Raça')


plt.savefig('grafico.png')


pdf = canvas.Canvas('grafico3.pdf')
pdf.setFont("Helvetica", 12)


pdf.drawImage('grafico.png', 100, 500, width=400, height=300)


texto = "Análise de dados por idade e raça"
largura_pagina = pdf._pagesize[0]
altura_imagem = 500
altura_texto = altura_imagem - 20
pdf.drawCentredString(largura_pagina / 2, altura_texto, texto)

pdf.save()
