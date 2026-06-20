# 📱 Digital Wallet App (Billetera Digital Básica)

¡Bienvenido al repositorio de **Digital Wallet App**! Este proyecto consiste en el desarrollo y optimización de una billetera digital interactiva de una sola cuenta. El principal objetivo del desafío fue migrar la lógica nativa de JavaScript hacia **jQuery** e implementar componentes dinámicos avanzados utilizando **Bootstrap**, logrando una experiencia de usuario fluida, robusta y con retroalimentación en tiempo real.

---

## 💡 Características principales y Desafíos Resueltos

El proyecto está dividido en 5 pantallas principales interconectadas de manera responsive:

### 🔐 1. Inicio de Sesión (`index.html`)
* **Selectores de jQuery:** Reemplazo de métodos nativos (`document.getElementById`) por la sintaxis concisa de jQuery (`$('#email').val()`) para la captura de credenciales.
* **Control de Formularios:** Manejo centralizado del evento de envío mediante `$('#loginForm').submit()`.
* **Alertas Dinámicas de Bootstrap:** Implementación de mensajes estilizados de éxito o error que reemplazan a los clásicos e invasivos `alert()` de JavaScript.
* **Redirección asistida:** Uso controlado del flujo de navegación para redirigir al menú principal tras una validación exitosa.

### 🗂️ 2. Menú Principal (`menu.html`)
* **Persistencia de Datos:** Carga automática del saldo dinámico del usuario consumiendo información desde el `LocalStorage`.
* **Eventos de Navegación con Leyenda:** Al interactuar con los botones principales (*Depositar, Enviar Dinero, Últimos Movimientos*), el sistema intercepta el clic y muestra una alerta dinámica informativa indicando la pantalla a la que está siendo redirigido antes de cambiar de ruta.

### 💰 3. Módulo de Depósito (`deposit.html`)
* **Saldo Previo en Pantalla:** Permite al usuario visualizar de forma clara su balance antes de operar.
* **Inyección Dinámica de Alertas:** Los mensajes de éxito se generan e insertan directamente en un contenedor DOM (`#alert-container`) mediante jQuery tras validar que el monto sea mayor a cero.
* **Confirmación de Operación:** Se incluye una leyenda descriptiva debajo del formulario detallando la cantidad exacta que se acaba de abonar.
* **Redirección con Temporizador:** Uso de `setTimeout` para retrasar la redirección al menú 2 segundos, garantizando que el usuario logre leer la confirmación de la transacción.

### 💸 4. Envió de Dinero y Agenda (`sendmoney.html`)
* **Interactividad nativa (Show/Hide):** Control absoluto con jQuery (`slideDown` / `slideUp`) para desplegar y ocultar el formulario de creación de contactos sin recargar la página.
* **Validación de Formularios:** Verificación estricta de campos obligatorios y formatos numéricos del CBU antes de procesar el alta de un nuevo destinatario.
* **Buscador en Tiempo Real:** Filtro inteligente en la agenda que evalúa coincidencias por **Nombre** o **Alias** a medida que el usuario escribe.
* **Botones Condicionales:** El botón principal para realizar la transferencia permanece oculto y sólo se revela (`fadeIn`) cuando se selecciona un contacto de la lista.
* **Control de Fondos:** Validación automática para impedir transferencias si el monto supera el saldo disponible.
* **Confirmación Inferior:** Banner de éxito al pie de la página confirmando la transferencia antes de retornar al menú.

### 📊 5. Historial de Transacciones (`transactions.html`)
* **Consumo de Datos Reales:** Se sustituyó la lista estática del HTML por la renderización dinámica de transacciones guardadas cronológicamente en el historial.
* **Filtro Avanzado por Tipo:** Inclusión de un selector dinámico que permite filtrar instantáneamente los movimientos según su naturaleza (*Depósitos/Entradas, Envíos/Compras o Mostrar Todo*).
* **Diseño Condicional:** Los elementos cambian de color automáticamente (clases `list-group-item-success` o `list-group-item-light` de Bootstrap) dependiendo de si representan un ingreso o un egreso de dinero.

---

## 🛠️ Tecnologías utilizadas

* **HTML5** & **CSS3** (Estructura y estilos personalizados).
* **Bootstrap 4.0** (Diseño responsive, grillas, formularios y componentes de alertas).
* **jQuery (3.x)** (Manipulación del DOM, gestión de eventos, animaciones de visibilidad y filtros).
* **Web Storage API (LocalStorage):** Para la persistencia del saldo y el historial de movimientos entre las diferentes pantallas.

---

## 🔑 Credenciales de Prueba

Para acceder y probar todas las funcionalidades de la aplicación, utiliza los siguientes datos en la pantalla de inicio de sesión (`index.html`):

* **Correo electrónico:** `user@wallet.com`
* **Contraseña:** `123456`

---

## 🚀 Cómo ejecutar el proyecto

1. Clona este repositorio en tu máquina local:
   ```bash
   git clone [https://github.com/odettegallo/Alke_Wallet.git](https://github.com/odettegallo/Alke_Wallet.git)
