def f(x):
    return x**2 - 2

def df(x):
    return 2 * x

x = 1.0

tolerance = 1e-6
max_iter = 30

print("Iteração |     x_n     |    f(x_n)   |   f'(x_n)   |   x_{n+1}")
print("-" * 60)

for i in range(max_iter):
    fx = f(x)
    dfx = df(x)
    
    if dfx == 0:
        print("Derivada zero! Algo deu errado.")
        break

    x_next = fx / dfx
    print(f"{i:5}     | {x:10.6f} | {fx:10.6f} | {dfx:10.6f} | {x_next:10.6f}")

    if abs(x_next - x) < tolerance:
        print("\nCritério de parada atingido.")
        break

    x = x_next
