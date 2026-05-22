[Anexo 4 - Banco de problemas - Fase 5.pdf](https://github.com/user-attachments/files/28131741/Anexo.4.-.Banco.de.problemas.-.Fase.5.pdf)
# Fase5_programacion
# Nombre: Joan Fernando Arias Morales
# Grupo: (213022A_2201)
# Programa: Ingenieria Electronica
# Codigo: Fuente propia

# 1. Matriz con 6 productos
menu = [["Hamburguesa Clasica", "Plato Principal", 25000],
    ["Pizza Margarita", "Plato Principal", 32000],
    ["Gaseosa", "Bebida", 5000],
    ["Cerveza Artesanal", "Bebida", 12000],
    ["Brownie con Helado", "Postre", 15000],
    ["Ensalada Cesar", "Entrada", 18000]]

# 2 y 3. Funcion y Logica de Negocio
def aplicar_promocion(producto, categoria_objetivo, precio_umbral):
    """
    Calcula el precio final aplicando un 15% de descuento si cumple las condiciones.
    """
    categoria_producto = producto[1]
    precio_base = producto[2]
    
    # Verificamos si pertenece a la categoria y supera el umbral
    if categoria_producto == categoria_objetivo and precio_base > precio_umbral:
        descuento = precio_base * 0.15
        return precio_base - descuento
    
    # Si no cumple, retorna el precio original
    return precio_base

# 4. Salida: Aplicacion de la promocion y visualizacion
categoria_promo = "Plato Principal"
umbral = 20000

print(f"--- APLICANDO PROMOCION: 15% en '{categoria_promo}' mayores a ${umbral} ---\n")

for item in menu:
    nombre = item[0]
    precio_base = item[2]
    
    # Llamamos al modulo para calcular el precio final
    precio_final = aplicar_promocion(item, categoria_promo, umbral)
    
    # Mostramos el resultado. Usamos int() para evitar decimales innecesarios en los precios
    if precio_base != precio_final:
        print(f"✅ {nombre}: Base ${precio_base} -> Final ${int(precio_final)} (¡Descuento aplicado!)")
    else:
        print(f"➖ {nombre}: Base ${precio_base} -> Final ${precio_base}")
