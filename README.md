# empleados
"""Construye dos superclases, donde una será la clase empleados que pida en consola el nombre
del empleado en un método de instancia.

La segunda clase será salario que pida en consola el salario del empleado en un método de instancia.

Cree una clase hija llamada Designación que herede las dos clases anteriores y que tenga un método de instancia
que designe el cargo del empleado.

Verifique el código, instanciando un objeto de la clase hija, verificando si el objeto tiene el método nombre y salario."""

class Empleado:
    def __init__(self):
        self.nombre = ""

    def ingresar_nombre(self):
        self.nombre = input("Ingrese el nombre del empleado: ")

class Salario:
    def __init__(self):
        self.salario = 0

    def ingresar_salario(self):
        self.salario = float(input("Ingrese el salario del empleado: "))

class Designacion(Empleado, Salario):
    def __init__(self):
        super().__init__()

    def asignar_cargo(self, cargo):
        self.cargo = cargo
        print(f"Se ha asignado el cargo: {cargo}")

# Verificación del código
if __name__ == "__main__":
    empleado_designado = Designacion()

    empleado_designado.ingresar_nombre()
    empleado_designado.ingresar_salario()
    empleado_designado.asignar_cargo("Gerente")

    # Verificar si el objeto tiene los métodos 'nombre' y 'salario'
    print(hasattr(empleado_designado, 'nombre'))  # Debería imprimir True
    print(hasattr(empleado_designado, 'salario'))  # Debería imprimir True
