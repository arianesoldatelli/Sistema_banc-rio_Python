# Sistema_bancario_Python
Criando um sistema bancário com Python

menu = """

[d] Depositar<br> 
[s] Sacar<br> 
[e] Extrato<br> 
[q] Sair<br> 

=> """

saldo= 0<br> 
limite= 500<br> 
extrato= "" #string<br> 
numero_saques = 0<br> 
LIMITE_SAQUES = 3<br> 

while True:

    opcao = input(menu)

    if opcao == "d":
        valor = float (input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Deposito: R$ {valor:.2f}\n"

        else: #valor<0
            print ("Não foi possível realizar a operação. Valor inválido.")

    
    if opcao == "s":
        valor = float (input("Informe o valor do saque: "))

        excedeu_saldo = valor> saldo
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print ("Saldo insuficiente. Por favor, tente novamente.")

        elif excedeu_limite:
            print ("Limite para saque R$500. Por favor, tente novamente.")

        elif excedeu_saques:
            print ("Limite de saques atingido. Por favor, tente novamente amanhã.")

        elif valor > 0:
            saldo -= valor
            extrato +def= f"Saque: R$ {valor:.2f}\n"
            numero_saques +=1

        else:
            print ("Não foi possível realizar a operação. O valor informado é inválido.")

    elif opcao == "e":
        print ("Não foram realizadas movimentações na conta." if not extrato else extrato)
        print (f"\nSaldo: R$ {saldo:.2f}")

    elif opcao == "q":
        break

    else: ("Operação inválida, por favor selecione novamente a opção desejada.")
