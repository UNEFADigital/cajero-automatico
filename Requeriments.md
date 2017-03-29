# Requerimientos

## 1. Características Generales del Proyecto

+ Máximo 3 usuarios con claves numéricas únicas serializadas en formato MD5 y saldo.
+ 8 botones contextuales (su acción cambia según la opción mostrada).
+ Cada usuario maneja dos cuentas, ahorro y corriente.
+ Persistencia (usando LocalStorage).
+ Control de retiros / de montos por retiro.
+ Teclado numérico con 4 botones adicionales (acciones de **CONTINUAR**, **CANCELAR**, **CORREGIR**, **COLOCAR**).
+ Visor de acciones del cajero.
+ Administración del saldo del cajero.

## 2. Historias de usuario.

+ [ ] Como usuario, quiero ver una interfaz similar a la de un cajero automático convencional (no inteligente). 4 botones a la izquierda, una caja con el visor y cajas de texto distribuidas con los botones externos y 4 botones a la derecha, un teclado numérico, del `0` al `9` con las teclas de `*` y `#` centrado respecto al visor, y en este teclado deben incluirse 4 botones con las acciones de **CONTINUAR** en color verde, **CANCELAR** en color rojo, **CORREGIR** en color amarillo y **COLOCAR** en color azul.
+ [ ] Como usuario, quiero tener una clave numérica única de 4 dígitos y manejar el saldo de dos cuentas, una de ahorros y una corriente, con las siguientes particularidades:
  + La cuenta de ahorros no me cobra comisión por ninguna operación, pero solo puedo hacer 2 operaciones diarias (retiro, transferencia o ambas), correspondientes al 5% de mi saldo diario en todos los casos.
  + La cuenta corriente cobra una comisión fija de Bs. 5 por operación (retiro, transferencia, consulta), pudiendo realizar hasta 3 retiros diarios y 3 transferencias por montos máximos según lo que permita el cajero.
  + Para ambas cuentas, las consultas de saldo son ilimitadas y no se cuentan en el límite de operaciones.
+ [ ] Como usuario, quiero poder realizar las operaciones de retiro, cambio de clave y consulta de saldo de ambos productos, respetando sus respectivas particularidades.
+ [ ] Como usuario, quiero poder transferir saldo entre mis productos (de mi cuenta de ahorros a mi cuenta corriente y viceversa), respetando las particularidades.
+ [ ] Como usuario, quiero indicar, en aquellas operaciones donde estén involucrados montos en bolívares, dichos montos con 2 decimales.
+ [ ] Como usuario, quiero ser notificado en caso de cada error, advertencia o éxito generado por la operación (clave de usuario incorrecta, saldo insuficiente, monto de transacción no permitido, monto máximo superado, monto de transferencia no permitido, límite de operaciones alcanzado, operación realizada con éxito, cajero sin efectivo disponible).
+ [ ] Como usuario, quiero realizar las siguientes acciones con los botones de acción del teclado numérico:
  + El botón **COLOCAR** me permite iniciar operaciones, este botón se debe deshabilitar durante todo el tiempo que se use el cajero y debe indicar que el cajero está ocupado con una señal alusiva (una marca o imagen circular girando en señal de "espera" es aceptable).
  + El botón **CONTINUAR** debe permitir iniciar operaciones luego de marcar la clave y que esta sea correcta. Si es incorrecta, debe notificarse inmediatamente al usuario.
  + El botón **CORREGIR** debe permitir borrar un caracter en cualquier campo editable que esté mostrando el visor.
  + El botón **CANCELAR** debe cancelar toda operación y volver al cajero a su estado original.
+ [ ] Como administrador, quiero tener una clave única de 16 dígitos que incluya `*` y `#` y no permita números separados.
+ [ ] Como administrador, quiero listar los productos financieros de los usuarios registrados en el cajero, con los saldos de cada uno de sus productos.
+ [ ] Como administrador, quiero modificar los valores por defecto del cajero automático: monto máximo de efectivo que maneja el cajero, cantidad de operaciones diarias del cajero, monto máximo por retiro, monto máximo por transferencia.
