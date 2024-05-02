def calcular_reajuste(salario_atual):
    if salario_atual <= 280.00:
        percentual_aumento = 20
    elif salario_atual <= 700.00:
        percentual_aumento = 15
    elif salario_atual <= 1500.00:
        percentual_aumento = 10
    else:
        percentual_aumento = 5

    aumento = salario_atual * (percentual_aumento / 100)
    novo_salario = salario_atual + aumento

    inflacao = 3.8
    aumento_real = aumento - (aumento * (inflacao / 100))

    return aumento, novo_salario, percentual_aumento, aumento_real

def main():
    salario_atual = float(input("Digite o salário atual do colaborador: R$"))

    aumento, novo_salario, percentual_aumento, aumento_real = calcular_reajuste(salario_atual)

    print(f"1. Salário antes do reajuste: R${salario_atual:.2f}")
    print(f"2. Percentual de aumento aplicado: {percentual_aumento}%")
    print(f"3. Valor do aumento: R${aumento:.2f}")
    print(f"4. Novo salário após o aumento: R${novo_salario:.2f}")
    print(f"5. Valor do aumento real descontado a inflação: R${aumento_real:.2f}")

if __name__ == "__main__":
    main()

