# Plan: checkout de demostración

## Objetivo

Crear un checkout estático con tres pasos visibles, un resumen coherente con `carrito.html` y sin recopilar datos ni simular una compra real.

## Archivos afectados

- **Crear `checkout.html`** en la raíz del proyecto.
- **Actualizar `carrito.html`** para enlazar al checkout una vez que exista.
- **Actualizar `specs/carrito/tasks.md`** para marcar la tarea condicional del enlace solo después de implementarlo y verificarlo.
- No modificar otros archivos.

## Orden recomendado

1. Crear `checkout.html` según [spec.md](spec.md): presentar en una página los pasos de datos personales, dirección de entrega y pago con tarjeta, un aviso visible de demostración y un enlace para volver al carrito.
2. Añadir un resumen coincidente con `carrito.html`: Camisa Claire, 89,00 €; Pantalón Jules, 125,00 €; Mocasines Étienne, 145,00 €; subtotal ilustrativo, 359,00 €; impuestos ilustrativos, 71,80 €; total ilustrativo, 430,80 €.
3. Mantener los campos como representación inactiva: sin formulario, envío de datos, información financiera real ni acción de compra. No añadir JavaScript propio, CSS adicional, frameworks ni dependencias.
4. Cuando exista `checkout.html`, añadir en `carrito.html` un enlace con destino válido al checkout.
5. Verificar ambas páginas y, solo después, marcar como completada la tarea condicional en `specs/carrito/tasks.md`.

## Verificación básica

- Abrir `checkout.html` directamente mediante el servidor estático y confirmar que carga.
- Comprobar la navegación entre carrito y checkout, y comparar productos e importes.
- Confirmar que los tres pasos aparecen en orden y que no se envían datos ni se simula una compra.
- Revisar navegación por teclado y presentación adaptable básica.

Este plan describe trabajo futuro; no significa que se haya implementado o verificado.
