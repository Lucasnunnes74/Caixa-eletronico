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

print('-'*10,'Banco Do Lucas','-'*10)
valor = int(input('''Qual valor você quer sacar R$:'''))
print('-'*34)
cinquenta = 0
vinte = 0
dez = 0
um = 0
qcinquenta = 10
qvinte = 10
qdez = 10
qum = 50
solicitado = valor
caixat = (qcinquenta * 50) + (qvinte * 20) + (qdez*10) + (qum * 1) 
dec = 0

while dec != 2:
    while valor != 0: 
        if qcinquenta == 0 and qvinte == 0 and qdez == 0 and qum == 0:      
            print(f'''{cores['vermelho']} Não tem cedulas o suficiente para saque.

            [Caixa em manutenção]{cores['term']}''')
            exit()
        while valor >= 50 and qcinquenta != 0:
            if valor >= 50:
                valor = valor - 50
                cinquenta += 1 
                qcinquenta -= 1        
        while valor >= 20 and qvinte != 0:
            if valor >= 20:
                valor = valor - 20
                vinte += 1
                qvinte -= 1 
        while valor >= 10 and qdez != 0:
            if valor >= 10:
                valor = valor - 10
                dez += 1
                qdez -= 1 
        while valor >= 1 and qum != 0:
            if valor >= 1:
                valor = valor - 1
                um += 1
                qum -= 1 
        if valor == 0:
            print(f'''{cores['verde']}O valor sacado de R$:{solicitado} foi realizado com sucesso

            Sendo:
            {cinquenta} cedulas de cinquenta reais
            {vinte} cedulas de Vinte 
            {dez} cedulas de Dez
            {um} cedulas de um
            ---------------------------------------
            
            Sobrou a seguinte quantidade de cedulas em caixa:
            {qcinquenta} cedulas de cinquenta reais
            {qvinte} cedulas de Vinte 
            {qdez} cedulas de Dez
            {qum} cedulas de um
            
            ---------O banco Lucas agradece---------{cores['term']}''')
            exit()     
        elif solicitado > caixat: 
            qcinquenta = cinquenta
            qvinte = vinte
            qdez = dez
            qum = um
            cinquenta = 0
            vinte = 0
            dez = 0
            um = 0
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
