class Calculadora:
    def somar(self, a, b):
        return a + b

    def subtrair(self, a, b):
        return a - b

    def multiplicar(self, a, b):
        return a * b

    def dividir(self, a, b):
        if b == 0:
            raise ValueError("Divisão por zero não é permitida.")
        return a / b


def main():
    calc = Calculadora()

    print("=== CALCULADORA POO ===")

    while True:
        print("\n1. Somar")
        print("2. Subtrair")
        print("3. Multiplicar")
        print("4. Dividir")
        print("5. Sair")

        opc = input("Opção: ")

        if opc == "5":
            print("Encerrando...")
            break

        if opc not in ["1", "2", "3", "4"]:
            print("Opção inválida!")
            continue

        try:
            n1 = float(input("Número 1: "))
            n2 = float(input("Número 2: "))
        except ValueError:
            print("Digite números válidos!")
            continue

        try:
            if opc == "1":
                print("Resultado:", calc.somar(n1, n2))
            elif opc == "2":
                print("Resultado:", calc.subtrair(n1, n2))
            elif opc == "3":
                print("Resultado:", calc.multiplicar(n1, n2))
            elif opc == "4":
                print("Resultado:", calc.dividir(n1, n2))
        except ValueError as e:
            print("Erro:", e)


if __name__ == "__main__":
    main()
