def apresentacao():
    print("Bem-vindo ao Sistema Especialista sobre Câncer.")
    print("Nosso objetivo é ajudar a identificar sinais de risco e fornecer orientações básicas.")
    print("Importante: Este sistema não substitui o diagnóstico médico. Consulte um profissional de saúde.\n")

def coleta_dados():
    print("Por favor, responda às perguntas a seguir com 'sim' ou 'não'.")
    historico_familiar = input("Há histórico de câncer na sua família? ").strip().lower()
    fumante = input("Você é ou foi fumante? ").strip().lower()
    idade_acima_de_50 = input("Você tem mais de 50 anos? ").strip().lower()
    sintomas = input("Você está apresentando sintomas como perda de peso inexplicada, dor persistente, ou caroços? ").strip().lower()
    return historico_familiar, fumante, idade_acima_de_50, sintomas

def avaliacao(historico_familiar, fumante, idade_acima_de_50, sintomas):
    print("\n--- Avaliação do Cenário ---")
    if historico_familiar == "sim" or fumante == "sim" or idade_acima_de_50 == "sim":
        print("Risco identificado: Com base nos fatores fornecidos, você pode estar em um grupo de maior risco.")
        if sintomas == "sim":
            print("Problema: Os sintomas relatados podem indicar um problema sério e devem ser investigados.")
            return "Alta prioridade para consulta médica."
        else:
            print("Problema: Apesar de não haver sintomas relatados, fatores de risco como idade, histórico familiar ou tabagismo são preocupantes.")
            return "Recomendação para avaliação médica preventiva."
    else:
        if sintomas == "sim":
            print("Problema: Os sintomas relatados são relevantes, mesmo sem outros fatores de risco.")
            return "Consulta médica recomendada para investigação dos sintomas."
        else:
            print("Nenhum risco imediato identificado com base nos dados fornecidos.")
            return "Continue com exames regulares e um estilo de vida saudável."

def solucao(recomendacao):
    print("\n--- Solução Sugerida ---")
    print(f"Sugestão: {recomendacao}")
    if "Alta prioridade" in recomendacao or "Consulta médica" in recomendacao:
        print("Procure um especialista em oncologia ou clínico geral o mais rápido possível.")
    else:
        print("Mantenha um acompanhamento médico regular e adote hábitos saudáveis como dieta equilibrada e prática de exercícios.")

def sistema_especialista():
    apresentacao()
    historico_familiar, fumante, idade_acima_de_50, sintomas = coleta_dados()
    recomendacao = avaliacao(historico_familiar, fumante, idade_acima_de_50, sintomas)
    solucao(recomendacao)

# Executar o sistema especialista
if __name__ == "__main__":
    sistema_especialista()
