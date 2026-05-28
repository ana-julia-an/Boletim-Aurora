# Função para calcular média das notas
def calcular_media(notas):
    return sum(notas) / len(notas)

# Função para calcular frequência (percentual de presença)
def calcular_frequencia(total_aulas, faltas):
    return ((total_aulas - faltas) / total_aulas) * 100 if total_aulas > 0 else 0

# Função para cadastrar dados do aluno e disciplinas
def cadastrar_dados():
    # Coletar dados básicos
    nome_aluno = input("Digite o nome do aluno: ")
    nome_escola = input("Digite o nome da escola: ")

    boletim = []
    disciplinas_validas = ["Língua Portuguesa", "Matemática", "Ciências", "Geografia", "História", "Educação Física", "Arte"]

    # Loop para cadastrar várias disciplinas
    while True:
        # Validação da disciplina
        disciplina = input("Escolha a disciplina (Língua Portuguesa, Matemática, Ciências, Geografia, História, Educação Física ou Arte): ")
        while disciplina not in disciplinas_validas:
            print("Disciplina inválida! Escolha uma das opções listadas.")
            disciplina = input("Escolha a disciplina: ")

        # Cadastro das notas com validação
        notas = []
        for i in range(1, 5):
            while True:
                try:
                    nota = float(input(f"Digite a nota do {i}º bimestre (0 a 10): "))
                    if 0 <= nota <= 10:
                        notas.append(nota)
                        break
                    else:
                        print("Nota inválida! Digite um valor entre 0 e 10.")
                except ValueError:
                    print("Entrada inválida! Digite um número.")

        # Cadastro das faltas com validação
        while True:
            try:
                faltas = int(input("Digite o número de faltas do aluno: "))
                if faltas >= 0:
                    break
                else:
                    print("Número de faltas inválido! Digite um valor maior ou igual a 0.")
            except ValueError:
                print("Entrada inválida! Digite um número inteiro.")

        # Processamento da média e situação
        media = calcular_media(notas)
        situacao = "APROVADO" if media >= 6.0 and faltas <= 25 else "REPROVADO"

        # Registro da disciplina no boletim
        registro = {
            "disciplina": disciplina,
            "notas": notas,
            "media": media,
            "faltas": faltas,
            "situacao": situacao
        }
        boletim.append(registro)

        # Pergunta se deseja continuar cadastrando
        continuar = input("Deseja registrar outra matéria? [s/n]: ")
        if continuar.lower() != "s":
            break

    return nome_aluno, nome_escola, boletim

# Função para gerar relatório final
def gerar_relatorio(nome_aluno, nome_escola, boletim):
    print("\n===== Boletim Aurora =====")
    print(f"Nome do aluno: {nome_aluno}")
    print(f"Escola: {nome_escola}\n")

    # Exibir cada disciplina cadastrada
    for item in boletim:
        print(f"Disciplina: {item['disciplina']}")
        print(f"Notas: {', '.join(str(n) for n in item['notas'])}")
        print(f"Média final: {item['media']:.2f}")
        print(f"Número de faltas: {item['faltas']}")
        print(f"Situação: {item['situacao']}\n")

# Programa principal
def main():
    nome_aluno, nome_escola, boletim = cadastrar_dados()
    gerar_relatorio(nome_aluno, nome_escola, boletim)

# Execução
if __name__ == "__main__":
    main()
