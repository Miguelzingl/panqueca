import random

def adivinha_numero():
    numero_secreto = random.randint(1, 100)
    tentativas = 0

    print("Bem-vindo ao jogo de Adivinhação!")
    print("Eu tenho um número entre 1 e 100. Tente adivinhá-lo!")

    while True:
        palpite = input("Digite seu palpite (ou 'sair' para encerrar): ")
        
        if palpite.lower() == 'sair':
            print("Obrigado por jogar!")
            break
        
        try:
            palpite = int(palpite)
            tentativas += 1
            
            if palpite < numero_secreto:
                print("Muito baixo! Tente novamente.")
            elif palpite > numero_secreto:
                print("Muito alto! Tente novamente.")
            else:
                print(f"Parabéns! Você adivinhou o número {numero_secreto} em {tentativas} tentativas.")
                break
        except ValueError:
            print("Por favor, insira um número válido.")

if __name__ == "__main__":
    adivinha_numero()
