# Python_Projeto

menu =  """
    [a]Depositar
    [b]Sacar
    [c]Extrato
    [d]Sair

=>"""

saldo=0
limite=500
extrato="0"
numeros_saques=0
LIMITES_SAQUES=3

while True:
    opcao=input(menu)

    if opcao == "a":
         
        valor=float(input("valor para depositar:"))
        if valor > 0:
           saldo += valor
           extrato+= f"saque é de:R${valor:.2f}\n"

           print(f"seu depósito é de:R${valor:.2f}\n")
          

           

        else:
             print('valor invalido')

    elif opcao == "b":

        valor=float(input("informe o valor do saque:"))

        excedeu_saque = valor > saldo 
        excedeu_limite = valor > limite
        excedeu_saques = numeros_saques >= LIMITES_SAQUES     

        if excedeu_saque:
            print('saldo insuficiente')

        elif excedeu_limite:
            print('excedeu o limite')

        elif excedeu_saques:
            print('não pode sacar mais')

        elif valor > 0 :
          saldo -= valor
          extrato+= f"saque é de:R${valor:.2f}\n"

          print( f"saque é de:R${valor:.2f}\n")
          extrato+= f"saque é de:R${valor:.2f}\n"
          numeros_saques +=1

        else:
            print('procedimento invalido')


    elif opcao == "c":
        print('extrato')
        print(f"\n saldo:R$ {saldo:.2f}\n")
        



    elif opcao == "d":
        break     

    else:
        print("ooperação inválida") 
        break




   
