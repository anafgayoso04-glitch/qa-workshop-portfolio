# Coverage Decisions

## Riesgos que se probarán primero

1. R1 - El sistema podría registrar el mismo pedido más de una vez si el usuario reintenta la operación.
2. R2 - El sistema podría mostrar productos sin stock como disponibles para comprar.
3. R3 - El usuario podría no realizar una compra porque no existe una opción para cambiar o recuperar su contraseña.

## ¿Por qué esos riesgos son prioridad?

Estos riesgos serán probados primero porque tienen un mayor impacto sobre el usuario y sobre el negocio.

El riesgo R1 es el más crítico, ya que podría generar pedidos duplicados y cobros incorrectos si el usuario reintenta una operación. Esto puede ocasionar reclamos de clientes, devoluciones y pérdidas para el negocio.

El riesgo R2 también debe ser priorizado porque un cliente podría realizar una compra de un producto que en realidad no se encuentra disponible. Esto obligaría al negocio a cancelar el pedido o realizar una devolución, generando una mala experiencia para el cliente.

El riesgo R3 es importante porque un usuario que no pueda cambiar o recuperar su contraseña podría no acceder a su cuenta y, por lo tanto, no completar una compra. Esto podría provocar abandono del proceso de compra y pérdida de ventas.

## Qué se probará menos o quedará fuera por ahora

- R4 - El sistema podría no actualizar inmediatamente la cantidad de productos en el carrito.
- R5 - El buscador de productos podría no devolver resultados aunque existan productos disponibles.

## Justificación de exclusiones

Los riesgos R4 y R5 serán probados con menor prioridad porque su impacto es menor en comparación con los riesgos relacionados con pedidos, disponibilidad de productos y acceso a la cuenta.

En el caso de R4, una actualización incorrecta o tardía de la cantidad de productos en el carrito puede generar confusión al usuario, pero no necesariamente impide que pueda continuar con el proceso de compra.

En el caso de R5, si el buscador no devuelve resultados correctamente, el usuario todavía podría localizar los productos navegando manualmente por el catálogo. Por este motivo, se considera un riesgo de menor impacto y puede ser probado después de cubrir los riesgos más importantes.

La estrategia de cobertura prioriza primero los escenarios que podrían generar pérdidas económicas, pedidos incorrectos, devoluciones o impedir que un cliente complete una compra.