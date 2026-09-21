# Sesión 1

## Charter

Explorar el proceso de selección y compra de productos, observando el comportamiento del sistema ante productos con disponibilidad limitada o sin stock, con el propósito de identificar si permite completar compras de productos que realmente no están disponibles.

## ÁREAS

Catálogo de productos, carrito de compras, disponibilidad de productos y proceso de compra.

## INICIO

Fecha: 20/09
Hora: 22:45
## TESTER

Ana Gayoso

## DESGLOSE DE TAREAS

- Inicio de sesión con usuario de prueba.
- Selección de productos del catálogo.
- Agregado de productos al carrito.
- Prueba con cantidad 1.
- Modificación de la cantidad a valores mayores a 1.
- Prueba con una cantidad elevada de 999 unidades.
- Procesamiento de la compra.
- Retroceso en el navegador luego de procesar una compra.
- Modificación y reprocesamiento del pedido.
- Observación del comportamiento relacionado con cantidades y disponibilidad.

## ARCHIVOS DE DATOS

- Usuario utilizado: 01
- Producto utilizado: K9-CW-01	Chihuahua, FL-DSH-01	Manx
- Cantidades probadas: 1, 2,3,4,5,15,20 y 999
- Otros datos utilizados: Datos de facturación y envío del usuario de prueba.

## NOTAS DE PRUEBA

- Se inició sesión correctamente con el usuario de prueba.
- Se seleccionó un producto y se agregó al carrito con cantidad 1.
- La operación con cantidad 1 se procesó correctamente.
- No se encontró información visible que indique cuántas unidades del producto existen actualmente en stock.
- Se modificó la cantidad del producto a 2 unidades y el sistema permitió continuar con el proceso de compra sin mostrar ningún mensaje de error o advertencia.
- Al procesar la operación, el sistema registró solamente 1 unidad en lugar de las 2 solicitadas.
- Se repitió la prueba utilizando una cantidad de 999 unidades.
- El sistema nuevamente permitió avanzar con la operación sin mostrar error, advertencia o información sobre disponibilidad.
- Al procesar la compra de 999 unidades, la operación terminó procesándose con cantidad 1.
- Por lo tanto, existe una diferencia entre la cantidad solicitada por el usuario y la cantidad finalmente procesada por el sistema.
- También se realizó una prueba utilizando la opción "Retroceder" del navegador después de completar una compra.
- Luego de retroceder, se modificó la cantidad de 1 a 2 y se intentó procesar nuevamente la operación.
- En este escenario, la pantalla final mostró una orden sin productos y un total de $0.00.
- La prueba fue repetida y el mismo comportamiento volvió a ocurrir.

## LISTA DE RIESGOS

- El usuario podría creer que está comprando una cantidad determinada cuando el sistema procesa una cantidad diferente.
- La ausencia de información visible de stock dificulta conocer cuántas unidades pueden adquirirse realmente.
- El sistema podría permitir avanzar con cantidades que no se encuentran disponibles.
- La falta de mensajes de validación puede generar confusión durante el proceso de compra.
- El uso de la opción "Retroceder" puede dejar el proceso de compra en un estado inconsistente.
- Podrían generarse órdenes incorrectas o vacías.

## DEFECTOS (BUGS)

### BUG-01 - El sistema procesa una cantidad diferente a la solicitada

**Descripción:**  
Al modificar la cantidad de un producto a un valor mayor a 1, el sistema permite continuar normalmente con el proceso de compra, pero finalmente procesa solamente una unidad.

**Pasos observados:**
1. Iniciar sesión.
2. Agregar un producto al carrito.
3. Modificar la cantidad de 1 a 2.
4. Continuar con el proceso de compra.
5. Verificar la cantidad procesada.
6. Repetir utilizando una cantidad de 999 unidades.

**Resultado esperado:**  
El sistema debería procesar la cantidad solicitada si existe disponibilidad o informar al usuario que la cantidad solicitada no se encuentra disponible.

**Resultado obtenido:**  
El sistema permite continuar sin advertencias, pero procesa únicamente cantidad 1.

**Reproducibilidad:**  
El comportamiento se reprodujo utilizando cantidades 2 y 999.

**Impacto:**  
El usuario podría creer que está comprando una cantidad determinada cuando realmente el sistema procesa otra diferente.

### BUG-02 - Orden vacía luego de retroceder y reprocesar la compra

**Descripción:**  
Después de completar una compra, utilizar la opción "Retroceder" del navegador, modificar la cantidad y volver a procesar la operación provoca que la pantalla final muestre una orden sin productos.

**Resultado esperado:**  
El sistema debería mantener un estado consistente del pedido o impedir que una operación ya procesada sea reprocesada incorrectamente.

**Resultado obtenido:**  
La orden aparece sin productos y con un total de $0.00.

**Reproducibilidad:**  
El comportamiento fue repetido y ocurrió nuevamente.

**Impacto:**  
Puede provocar órdenes inconsistentes y confusión para el cliente.

## INCIDENTES (ISSUES)

### ISSUE-01 - No se muestra información de stock disponible

Durante la exploración no se encontró información visible que indique la cantidad de unidades disponibles de cada producto.

No es posible determinar únicamente mediante la interfaz si un producto tiene una, varias o ninguna unidad disponible.

Esto dificulta confirmar si el comportamiento observado al solicitar cantidades superiores a 1 se debe a una limitación real de stock o a un defecto en el procesamiento de cantidades.