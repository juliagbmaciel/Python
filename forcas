import funcoes_jogo
import main


def nutella():

    while True:

        palavra_sorteada = funcoes_jogo.palavra_random()
        palavra_acerto = ['_']*len(palavra_sorteada)
        vidas = 6
        letras_erradas = []
        funcoes_jogo.cabecalho('NUTTELA')
        print(f"A palavra sorteada possui {len(palavra_sorteada)} letras.")
        dica, dicas = funcoes_jogo.obter_dica(palavra_sorteada)
        print(f'A dica desta palavra é: {dica}')

        while vidas > 0:

            funcoes_jogo.exibicao(vidas, palavra_acerto)

            letra_chute = input("\nDigite uma letra como chute: ").lower()

            funcoes_jogo.letra_duplicada(letra_chute, letras_erradas, palavra_acerto)
            funcoes_jogo.letra_correta(palavra_sorteada, letra_chute, palavra_acerto)

            if funcoes_jogo.verificar_acerto(palavra_acerto, palavra_sorteada, vidas, letra_chute):
                break

            vidas = funcoes_jogo.verificar_erro(palavra_sorteada, letras_erradas, letra_chute, vidas)

        if vidas <= 0 and palavra_acerto != palavra_sorteada:
            op = input("Infelizmente você perdeu! Deseja tentar outra vez? [S/N]").upper()

            if op == 'S':
                main.menuzin()
            elif op == 'N':
                print("Obrigada pela participação!! Tchau Tchau...")
                funcoes_jogo.encerrar()
            elif op != 'S':
                print('Digite uma opção válida, apenas S ou N.')
        else:
            op = input("Deseja tentar outra vez? [S/N]\n").upper()
            if op == 'S':
                main.menuzin()
            if op == 'N':
                print("Obrigada pela participação!! Tchau Tchau...")
                funcoes_jogo.encerrar()
            elif op != 'S':
                print('Digite uma opção válida, apenas S ou N.')


def cafe_com_leite():

    while True:

        palavra_sorteada, dicas = funcoes_jogo.palavra_random_cafe()
        dica_palavra = funcoes_jogo.obter_dica_cafe(dicas, palavra_sorteada)
        print("Você tem 30 segundos para adivinhar a palavra")
        print(f"A palavra sorteada possui {len(palavra_sorteada)} letras.")
        print(f'A dica desta palavra é: {dica_palavra}')
        palavra_acerto = ['_'] * len(palavra_sorteada)
        vidas = 6
        letras_erradas = []

        inicio_tempo = funcoes_jogo.comecar_tempo()

        while vidas > 0:

            funcoes_jogo.exibicao(vidas, palavra_acerto)

            letra_chute = input("\nDigite uma letra como chute: ").lower()

            funcoes_jogo.letra_duplicada(letra_chute, letras_erradas, palavra_acerto)
            funcoes_jogo.letra_correta(palavra_sorteada, letra_chute, palavra_acerto)

            if funcoes_jogo.verificar_acerto(palavra_acerto, palavra_sorteada, vidas, letra_chute):
                inicio_tempo.cancel()
                break

            vidas = funcoes_jogo.verificar_erro(palavra_sorteada, letras_erradas, letra_chute, vidas)

        if vidas <= 0 and palavra_acerto != palavra_sorteada:
            inicio_tempo.cancel()
            op = input(f"Infelizmente você perdeu!\nA palavra sorteada era {palavra_sorteada}"
                       f"\n Deseja tentar outra vez? [S/N]").upper()

            if op == 'S':
                main.menuzin()
            elif op == 'N':
                print("Obrigada pela participação!! Tchau Tchau...")
                funcoes_jogo.encerrar()
            elif op != 'S':
                print('Digite uma opção válida, apenas S ou N.')
        else:
            inicio_tempo.cancel()
            op = input("Deseja tentar outra vez? [S/N]\n").upper()
            if op == 'S':
                main.menuzin()
            elif op == 'N':
                print("Obrigada pela participação!! Tchau Tchau...")
                funcoes_jogo.encerrar()
            elif op != 'S':
                print('Digite uma opção válida, apenas S ou N.')

def raiz():

    while True:
        funcoes_jogo.cabecalho('RAIZ')
        palavra_sorteada, dicas = funcoes_jogo.api()
        print("Você tem 30 segundos para adivinhar a palavra")
        print(f"A palavra sorteada possui {len(palavra_sorteada)} letras.")
        print(f'A dica desta palavra é: {dicas}')
        palavra_acerto = ['_'] * len(palavra_sorteada)
        vidas = 6
        letras_erradas = []

        inicio_tempo = funcoes_jogo.comecar_tempo()

        while vidas > 0:

            funcoes_jogo.exibicao(vidas, palavra_acerto)

            letra_chute = input("\nDigite uma letra como chute: ").lower()

            funcoes_jogo.letra_duplicada(letra_chute, letras_erradas, palavra_acerto)
            funcoes_jogo.letra_correta(palavra_sorteada, letra_chute, palavra_acerto)

            if funcoes_jogo.verificar_acerto(palavra_acerto, palavra_sorteada, vidas, letra_chute):
                inicio_tempo.cancel()
                break

            vidas = funcoes_jogo.verificar_erro(palavra_sorteada, letras_erradas, letra_chute, vidas)

        if vidas <= 0 and palavra_acerto != palavra_sorteada:
            inicio_tempo.cancel()
            op = input(f"Infelizmente você perdeu!\nA palavra sorteada era {palavra_sorteada}"
                       f"\n Deseja tentar outra vez? [S/N]").upper()

            if op == 'S':
                main.menuzin()
            elif op == 'N':
                print("Obrigada pela participação!! Tchau Tchau...")
                funcoes_jogo.encerrar()
            elif op != 'S':
                print('Digite uma opção válida, apenas S ou N.')
        else:
            inicio_tempo.cancel()
            op = input("Deseja tentar outra vez? [S/N]\n").upper()
            if op == 'S':
                main.menuzin()
            elif op == 'N':
                print("Obrigada pela participação!! Tchau Tchau...")
                funcoes_jogo.encerrar()
            elif op != 'S':
                print('Digite uma opção válida, apenas S ou N.')
