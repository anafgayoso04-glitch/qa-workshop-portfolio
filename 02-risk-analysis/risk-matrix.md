# Risk Matrix

| ID | Riesgo | Impacto | Probabilidad | Nivel | Justificación |
|----|--------|---------|--------------|-------|---------------|
| R1 | El sistema podría registrar el mismo pedido más de una vez si el usuario reintenta la operación | Alto | Alta | Crítico | Puede producir pedidos duplicados y cobros incorrectos |
| R2 | El sistema podría mostrar productos sin stock como disponibles para comprar | Alto | Media | Alto | El cliente podría realizar la compra y luego sería necesario cancelar el pedido o realizar una devolución por falta de stock |
| R3 | El usuario podría no realizar una compra porque no existe una opción para cambiar o recuperar su contraseña | Medio | Alta | Alto | Si el usuario no puede acceder a su cuenta, podría abandonar la compra y el negocio perder una venta |
| R4 | El sistema podría no actualizar inmediatamente la cantidad de productos en el carrito | Medio | Media | Medio | Puede generar confusión en el usuario y errores al revisar su compra, aunque no necesariamente impide finalizarla |
| R5 | El buscador de productos podría no devolver resultados aunque existan productos disponibles | Bajo | Media | Bajo | El usuario todavía puede buscar el producto manualmente navegando por el catálogo |