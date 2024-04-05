def adicionar(n1,n2):
    return n1+n2

def subtrair(n1,n2):
    return n1-n2

def multiplicar(n1,n2):
    return n1*n2


def dividir(n1,n2):
    return n1/n2


operações = {"+": adicionar,
             "-": subtrair,
             "*": multiplicar,
             "/": dividir}

def calculadora():
    num1 = float(input("Qual o primeiro número?"))



    for simbolo in operações:
        print(simbolo)
    deve_continuar = True

    while deve_continuar:
        simbolo_operação = input("Escolha uma operação:")
        num2 = float(input("Qual o próximo número?"))
        função_calculadora = operações[simbolo_operação]
        resposta = função_calculadora(num1, num2)
            
        print(f"{num1} {simbolo_operação} {num2} = {resposta}" )


        if input(f"Digite s para continuar a calcular com {resposta} ou digite n para começar um cálculo do zero: ") == "s":
            num1 = resposta
        else:
            deve_continuar = False
            calculadora()
            
            
calculadora()
