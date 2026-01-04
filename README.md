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
```
2. Crear y activar un entorno virtual::
```bash
python3 -m venv venv
source venv/bin/activate
```
3. Instalar dependencias:
```bash
pip install -r requirements.txt
```
4. Instalar y habilitar Mosquitto:
```bash
sudo apt install mosquitto mosquitto-clients
sudo systemctl enable mosquitto
sudo systemctl start mosquitto
```
5. Ejecutar el sistema:
```bash
sudo python3 FaceID.py
```

## 🎮 Uso del sistema

### 🔔 Reconocimiento facial
1. Presionar el botón físico.
2. El sistema captura la imagen y realiza el reconocimiento.
3. En la web se muestra:
    -Imagen capturada
    -Nombre reconocido (si existe coincidencia)
    -Porcentaje de similitud
4. Desde la web se puede:
    -Permitir acceso → el servo abre la cerradura
    -Denegar acceso → no se acciona el servo

### 👤 Registro de nuevos usuarios
   
1. Presionar Registrar nuevo rostro en la web.
2. Ingresar el nombre del usuario.
3. Presionar el botón físico.
4. El rostro queda almacenado para futuros reconocimientos.

## 🧩 Componentes utilizados
### Hardware
* Raspberry Pi 3 Model B
* Cámara USB
* Servomotor SG90
* LED RGB
* Botón físico
* Fuente de alimentación 5V

###Software
* Python 3
* OpenCV
* MTCNN
* FaceNet (Keras / TensorFlow)
* NumPy
* Flask
* MQTT (Mosquitto)
* HTML, CSS y JavaScript

## 📂 Estructura del proyecto
* FaceID.py – Lógica principal del sistema
* embeddings.txt – Base de datos de embeddings faciales
* names.txt – Nombres asociados a cada embedding
* index.html – Interfaz web
* script.js – Lógica del cliente web y MQTT
* requirements.txt – Dependencias del proyecto

## 🎯 Objetivo del proyecto
Desarrollar un sistema de autenticación biométrica funcional y educativo, que permita comprender el funcionamiento del reconocimiento facial y su integración con hardware e interfaces web.

## 👨‍💻 Autores
* Ignacio Faccipieri
* Matías Rodriguez Aguiar
* Fausto Graciano Gonzalez


