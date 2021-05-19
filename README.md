# Caixa-eletronico




cores = {'term':'\033[m', 
        'azul': '\033[34m',
        'branco': '\033[30m',
        'vermelho': '\033[31m',
        'verde': '\033[32m',
        'amarelo': '\033[33m',
        'rosa': '\033[35m],',
        'azulC': '\033[36',
        'cinza': '\033[37' }

valores = [int(0), int(0), int(0), int(0) ]
quantidadeV = [int(10), int(10), int(10), int(10) ]
caixat = (quantidadeV[0] * 50) + (quantidadeV[1] * 20) + (quantidadeV[2] *10) + (quantidadeV[3] * 1) 
dec = 0

while True:
    print('-'*10,'Banco Do Lucas','-'*10)
    valor = int(input('''Qual valor você quer sacar R$:'''))
    print('-'*34)
    solicitado = valor
    while valor != 0:
        if quantidadeV[0] == 0 and quantidadeV[1] == 0 and quantidadeV[2] == 0 and quantidadeV[3] == 0:      
            print(f'''{cores['vermelho']} Não tem cedulas o suficiente para saque.

            [Caixa em manutenção]{cores['term']}''')
            exit()
        while valor >= 50 and quantidadeV[0] != 0:       
            valor = valor - 50
            valores[0] += 1 
            quantidadeV[0] -= 1        
        print('pulei')
        while valor >= 20 and quantidadeV[1] != 0:
            valor = valor - 20
            valores[1] += 1 
            quantidadeV[1] -= 1  
        while valor >= 10 and quantidadeV[2] != 0:
            valor = valor - 10
            valores[2] += 1 
            quantidadeV[2] -= 1 
        while valor >= 1 and quantidadeV[3] != 0:
            valor = valor - 1
            valores[3] += 1 
            quantidadeV[3] -= 1 
        if valor == 0:
            print(f'''{cores['verde']}O valor sacado de R$:{solicitado} foi realizado com sucesso

            Sendo:
            {valores[0]} cedulas de cinquenta reais
            {valores[1]} cedulas de Vinte 
            {valores[2]} cedulas de Dez
            {valores[3]} cedulas de um
            ---------------------------------------
            
            Sobrou a seguinte quantidade de cedulas em caixa:
            {quantidadeV[0]} cedulas de cinquenta reais
            {quantidadeV[1]} cedulas de Vinte 
            {quantidadeV[2]} cedulas de Dez
            {quantidadeV[3]} cedulas de um
            
            ---------O banco Lucas agradece---------{cores['term']}''')
            exit()     
        elif solicitado > caixat: 
            quantidadeV[0] = valores[0]
            quantidadeV[1] = valores[1]
            quantidadeV[2] = valores[2]
            quantidadeV[3] = valores[3]
            valores[0] = 0
            valores[1] = 0
            valores[2] = 0
            valores[3] = 0
            print(f'''{cores['vermelho']}Não tem valor suficiente em caixa{cores['term']}''')

            print(f'por gentileza solicitar valor até R$:{caixat}')
            print('-'*34)
            dec = int(input('''Ainda deseja sacar: 
            [1] Sim
            [2] Não
            Resposta: '''))   
        if dec == 1:
            valor = int(input('''
            Qual valor você quer sacar R$:'''))
            print('-'*34)
        else:
            print(f'---------O banco Lucas agradece---------')   
            print(f'--------------Volte Sempre--------------') 
            exit()           
    print('Por gentileza digitar um valor maior que R$: 0')
