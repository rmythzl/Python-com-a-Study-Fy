# 📝 Task Manager em Python

Projeto simples de **Gerenciador de Tarefas** desenvolvido em Python, voltado para iniciantes que desejam aprender lógica de programação de forma prática, clara e objetiva.

---

## 🎯 Objetivo do Projeto

Este projeto tem como objetivo ensinar conceitos básicos da linguagem Python, como:

- Variáveis
- Listas
- Funções
- Condições (`if / else`)
- Laços de repetição (`while`)
- Entrada de dados pelo terminal (`input`)

Tudo isso utilizando um sistema simples e fácil de entender.

---

## 🧠 Como o projeto funciona

O programa roda no **terminal** e apresenta um menu interativo com as seguintes opções:

1. Adicionar uma tarefa  
2. Listar tarefas cadastradas  
3. Remover uma tarefa  
4. Encerrar o programa  

O usuário escolhe a opção digitando o número correspondente no teclado.

---

## 📁 Estrutura do Projeto


---

## 🐍 Código do Projeto (`src/main.py`)

```python
# Projeto: Gerenciador de Tarefas em Python
# Autor: Rian Gabriel Pires Barbalha
# Patrocínio educacional: Study Fy

def mostrar_menu():
    print("\n=== GERENCIADOR DE TAREFAS ===")
    print("1 - Adicionar tarefa")
    print("2 - Listar tarefas")
    print("3 - Remover tarefa")
    print("4 - Sair")


def adicionar_tarefa(tarefas):
    tarefa = input("Digite a tarefa: ")
    tarefas.append(tarefa)
    print("✅ Tarefa adicionada com sucesso!")


def listar_tarefas(tarefas):
    if len(tarefas) == 0:
        print("📭 Nenhuma tarefa cadastrada.")
    else:
        print("\n📋 Lista de tarefas:")
        for indice, tarefa in enumerate(tarefas):
            print(f"{indice + 1} - {tarefa}")


def remover_tarefa(tarefas):
    listar_tarefas(tarefas)
    if len(tarefas) > 0:
        try:
            numero = int(input("Digite o número da tarefa para remover: "))
            tarefas.pop(numero - 1)
            print("🗑️ Tarefa removida com sucesso!")
        except:
            print("❌ Número inválido!")


def main():
    tarefas = []

    while True:
        mostrar_menu()
        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            adicionar_tarefa(tarefas)
        elif opcao == "2":
            listar_tarefas(tarefas)
        elif opcao == "3":
            remover_tarefa(tarefas)
        elif opcao == "4":
            print("👋 Programa encerrado. Até mais!")
            break
        else:
            print("❌ Opção inválida!")


main()

