# 1. Função: Números Primos em Intervalo
def primos_no_intervalo(a, b):
    """Retorna uma lista com todos os números primos entre a e b (inclusive)."""
    primos = []
    for num in range(max(2, a), b + 1):
        for i in range(2, int(num ** 0.5) + 1):
            if num % i == 0:
                break
        else:
            primos.append(num)
    return primos


# 2. Função: Ordena e Remove Duplicatas
def ordenar_sem_repeticao(lista):
    """Retorna uma lista ordenada sem elementos repetidos."""
    return sorted(set(lista))


# 3. Função: Soma dos Dígitos
def soma_digitos(n):
    """Retorna a soma dos dígitos de um número inteiro."""
    return sum(int(digito) for digito in str(abs(n)))


# 4. Função: Palíndromo
def eh_palindromo(texto):
    """Verifica se uma string é palíndroma (ignora maiúsculas/minúsculas e espaços)."""
    texto_limpo = ''.join(c.lower() for c in texto if c.isalnum())
    return texto_limpo == texto_limpo[::-1]


# 5. Função: Frequência de Palavras
def frequencia_palavras(texto):
    """Retorna um dicionário com a frequência de cada palavra em uma frase."""
    palavras = texto.lower().split()
    freq = {}
    for palavra in palavras:
        palavra_limpa = ''.join(c for c in palavra if c.isalnum())
        freq[palavra_limpa] = freq.get(palavra_limpa, 0) + 1
    return freq


# 6. Função: Média dos Elementos
def media_lista(lista):
    """Retorna a média dos elementos de uma lista. Se estiver vazia, retorna None."""
    if not lista:
        return None
    return sum(lista) / len(lista)


# --------------------------
# Testes das funções
# --------------------------
if __name__ == "__main__":
    print("1. Primos entre 10 e 30:", primos_no_intervalo(10, 30))
    print("2. Ordenar sem repetição:", ordenar_sem_repeticao([4, 2, 2, 3, 1, 4]))
    print("3. Soma dos dígitos de -12345:", soma_digitos(-12345))
    print("4. É palíndromo ('Ame a ema'):", eh_palindromo("Ame a ema"))
    print("5. Frequência de palavras:", frequencia_palavras("O rato roeu a roupa do rei de Roma"))
    print("6. Média da lista [10, 20, 30]:", media_lista([10, 20, 30]))
    print("6. Média da lista vazia:", media_lista([]))
