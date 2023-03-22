import random
from threading import Timer
import os
import requests
from xml.dom import minidom



# sorteia uma palavra, e pergunta se o usuario quer adicionar uma para iniciar o jogo
def palavra_random_cafe():
    while True:
        cabecalho()
        dica, dicas = obter_dica('azul')
        palavras = ['banana', 'azul', 'vermelho', 'pipoca', 'sandalia',
                    'trabalho', 'simpatia', 'cavalo', 'estojo', 'caneta',
                    'nariz', 'boca', 'carregador', 'portaria']
        op = input("Deseja inserir uma nova palavra? [SIM OU NAO] \n").upper()
        if op == 'SIM':
            qtd_palavras = int(input("Quantas palavras quer inserir?\n"))
            for i in range(qtd_palavras):
                nova_palavra = input(f"Digite a {i+1}° palavra: ")
                while True:
                    op_dica = input("Deseja inserir uma dica a esta palavra? [SIM OU NAO]\n").upper()
                    if op_dica == 'SIM':
                        dica_usuario = input("Digite a sua dica: ")
                        dicas[nova_palavra] = dica_usuario
                        break
                    elif op_dica != 'SIM':
                        dicas[nova_palavra] = 'Palavra digitada pelo usuário, que optou não inserir dicas.'
                        print("OK")
                        break
                palavras.append(nova_palavra)
                print(dicas)
            return random.choice(palavras), dicas
        elif op == 'NAO':
            print("OK, Obrigada.")
            return random.choice(palavras), dicas
        elif op != 'SIM' and op != 'NAO':
            print("Por favor, digite apenas sim ou nao.")


def palavra_random():
    palavras = ['banana', 'azul', 'vermelho', 'pipoca', 'sandalia',
                'trabalho', 'simpatia', 'cavalo', 'estojo', 'caneta',
                'nariz', 'boca', 'carregador', 'portaria']
    return random.choice(palavras)


# a = dicas, b = palavra_sorteada
def obter_dica_cafe(a, b):
    c = a.get(b).lower()
    return c


def obter_dica(a=" "):
    dicas = {
        'banana': 'Fruta amarela',
        'azul': 'Cor do céu em um dia claro',
        'vermelho': 'Cor da paixão',
        'pipoca': 'Lanche de cinema',
        'sandalia': 'Calçado de verão',
        'trabalho': 'Atividade remunerada',
        'simpatia': 'Gesto ou palavra que visa atrair boa sorte',
        'cavalo': 'Animal de porte alto',
        'estojo': 'Item escolar para guardar lápis e canetas',
        'caneta': 'Instrumento de escrita',
        'nariz': 'Órgão do olfato',
        'boca': 'Órgão da fala e alimentação',
        'carregador': 'Usado para carregar bateria de dispositivos eletrônicos',
        'portaria': 'Local de entrada em um edifício ou condomínio'
    }
    dica = dicas.get(a).lower()
    return dica, dicas


# imprime o cabeçalho do jogo
def cabecalho(a='CAFE COM LEITE'):
    print('-' * 40)
    print('  ' * 4, f'MODO: {a}', '  ' * 4)
    print('-' * 40)


# v = vidas, j = palavra_acerto
def exibicao(v, j):
    print(f"Chances: {v}")
    for i in j:
        print(i, end=' ')


# a = letra_chute, b = letras_erradas, c = palavra_acerto
def letra_duplicada(a, b, c):
    if a in c:
        print("Oh Oh, essa letra já foi digitada e já está na palavra, tente outra!")
    elif a in b:
        print("Oh Oh, essa letra já foi digitada, tente outra!")
        print(b)


# a = palavra_sorteada, b = letra_chute, c = palavra_acerto
def letra_correta(a, b, c):
    for y in range(len(a)):
        if b == a[y]:
            c[y] = b


# a = palavra_acerto, b = palavra_sorteada, c = vidas, d = letra_chute
def verificar_acerto(a, b, c, d):
    if ''.join(a) == b or d == b:
        a = b
        exibicao(c, a)
        print("\nParabéns c: Você venceu!!!")
        print(f"A palavra sorteada era {b}")
        return True

    return False


# a = palavra_sorteada,b = letras_erradas,c = letra_chute, d = vidas
def verificar_erro(a, b, c, d):
    if c not in a and c not in b:
        print("Oh não! Essa letra não faz parte da palavra!")
        b.append(c)
        print(b)
        d -= 1

    return d


def comecar_tempo():
    inicio_tempo = Timer(30, fim_tempo)
    inicio_tempo.start()
    return inicio_tempo


def cancel(inicio_tempo):
    inicio_tempo.cancel()


def fim_tempo():
    print("\33[1;41mFim de jogo!! Acabou o seu tempo!!\33[0m")
    pid = os.getpid()
    os.kill(pid, 0)

def encerrar():
    pid = os.getpid()
    os.kill(pid, 0)

def api():
    dica = ' '

    proxy = {
        'http': 'http://ct67ca:23%23INDUSTRIAdigital@proxy.br.bosch.com:8080',
        'https': 'http://ct67ca:23%23INDUSTRIAdigital@proxy.br.bosch.com:8080'
    }

    url = 'https://api.dicionario-aberto.net/random'

    response1 = requests.get(url, proxies=proxy)
    palavra_sorteada = response1.json()['word']

    url2 = f'https://api.dicionario-aberto.net/word/{palavra_sorteada}'

    response2 = requests.get(url2, proxies=proxy)

    xml = response2.json()[0]['xml']

    parsed_xml = minidom.parseString(xml)
    elementos = parsed_xml.getElementsByTagName('def')

    for element in elementos:
        dica = element.firstChild.nodeValue

    return palavra_sorteada, dica
