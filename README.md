# JogoDaForcaPython
Um jogo simples de forca em Python, onde o jogador deve adivinhar uma palavra oculta antes de esgotar o número de tentativas.
Python 3.12.2 (tags/v3.12.2:6abddd9, Feb  6 2024, 21:26:36) [MSC v.1937 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import random
>>>
>>> def jogar_forca():
...     palavras = ['python', 'programacao', 'desafio', 'computador', 'jogo', 'aprender', 'divertido']
...     palavra = random.choice(palavras)
...     letras_certas = []
...     letras_erradas = []
...     tentativas = 6
...
...     while True:
...         palavra_mascarada = ''
...         for letra in palavra:
...             if letra in letras_certas:
...                 palavra_mascarada += letra
...             else:
...                 palavra_mascarada += '_'
...
...         print(f"Palavra: {palavra_mascarada}")
...         print(f"Tentativas restantes: {tentativas}")
...         print(f"Letras erradas: {', '.join(letras_erradas)}")
...
...         if palavra_mascarada == palavra:
...             print("Parabéns, você venceu!")
...             break
...
...         if tentativas == 0:
...             print(f"Game over! A palavra era: {palavra}")
...             break
...
...         letra = input("Digite uma letra: ")
...         if len(letra) != 1 or not letra.isalpha():
...             print("Por favor, digite apenas uma letra.")
...             continue
...
...         if letra in letras_certas or letra in letras_erradas:
...             print("Você já tentou essa letra. Tente novamente.")
...             continue
...
...         if letra in palavra:
...             letras_certas.append(letra)
...         else:
...             letras_erradas.append(letra)
...             tentativas -= 1
...
>>> jogar_forca()
Palavra: _________
Tentativas restantes: 6
Letras erradas:
Digite uma letra: a
Palavra: _________
Tentativas restantes: 5
Letras erradas: a
Digite uma letra: m
Palavra: _________
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: r
Palavra: ____r____
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: d
Palavra: d___r__d_
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: i
Palavra: di__r_id_
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: v
Palavra: div_r_id_
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: e
Palavra: diver_id_
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: t
Palavra: divertid_
Tentativas restantes: 4
Letras erradas: a, m
Digite uma letra: o
Palavra: divertido
Tentativas restantes: 4
Letras erradas: a, m
Parabéns, você venceu!
>>>
