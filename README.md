# 🔐 FaceID – Sistema de control de acceso con reconocimiento facial

## 📖 Descripción

Este proyecto consiste en un **sistema de control de acceso mediante reconocimiento facial**, desarrollado como trabajo práctico para la materia *Taller de Proyecto II*.  
El objetivo es implementar una solución **de bajo costo**, inspirada en productos comerciales como **Face ID de Apple**, **Ring de Amazon** o **Google Nest**, utilizando hardware accesible y software de código abierto.

El sistema permite:
- Reconocer rostros previamente registrados.
- Mostrar el resultado del reconocimiento en una interfaz web.
- Permitir o denegar el acceso de forma manual.
- Accionar una cerradura simulada mediante un servomotor.

La comunicación entre la Raspberry Pi y la interfaz web se realiza mediante el protocolo **MQTT**.

---

## ⚙️ ¿Cómo funciona?

1. Un usuario presiona el **botón físico (timbre)**.
2. La cámara captura una imagen del rostro.
3. Se detecta el rostro y se genera su **embedding**.
4. El embedding se compara con los embeddings almacenados.
5. El resultado se envía a la **interfaz web**.
6. Desde la web se decide permitir o denegar el acceso.
7. Según la decisión, se acciona o no el servomotor.

---

## ▶️ Ejecución del programa

### Requisitos
- Raspberry Pi con sistema operativo Linux
- Cámara USB
- Servomotor, LED RGB y botón físico
- Python 3
- Broker MQTT (Mosquitto)

### Instalación

1. Clonar el repositorio:
```bash
git clone https://github.com/NachoFaccipieri/TP2
cd TP2/EntregaFinal

