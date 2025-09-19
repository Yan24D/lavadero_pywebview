# 🚗 Lavadero PyWebView

## 📌 Descripción
Aplicación de escritorio para la gestión de un lavadero de vehículos.  
Este sistema utiliza **Python + PyWebView** para la interfaz de usuario y **MySQL** como base de datos.  

Se gestiona mediante **dos roles de usuario**:
- **Administrador**: manejo de reportes, usuarios y roles, edición de servicios y precios, finanzas e historial.
- **Secretario**: registro de vehículos, historial de servicios y cierre de caja.

---

## 🎯 Características principales
- Inicio de sesión con roles: **Admin** y **Secretario**.
- Registro de vehículos con datos del cliente.
- Consulta de historial de servicios.
- Cierre de caja diario.
- Panel de administración con reportes y finanzas.
- Gestión de usuarios y servicios.

---

## 📂 Estructura del proyecto
```
lavadero_pywebview/
│── README.md                # Documentación del proyecto
│── requirements.txt         # Dependencias de Python
│── main.py                  # Punto de entrada de la app
│── config.py                # Configuración global (ej. conexión DB)
│── .env                     # Variables de entorno (credenciales DB)
│
├── backend/                 # Lógica de negocio
│   ├── __init__.py
│   ├── database.py          # Conexión a MySQL
│   ├── models.py            # Modelos (Usuarios, Vehículos, Servicios)
│   ├── controllers.py       # Funciones de negocio (login, caja, reportes)
│   └── utils.py             # Funciones auxiliares
│
├── frontend/                # Interfaz (HTML, CSS, JS)
│   ├── login.html           # Pantalla de inicio de sesión
│   ├── dashboard_admin.html # Panel del administrador
│   ├── dashboard_sec.html   # Panel del secretario
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── scripts.js
│
├── assets/                  # Recursos estáticos
│   ├── img/                 # Logos, íconos
│   └── fonts/               # Tipografías si las usas
│
└── build/                   # Carpeta de salida para empaquetar con PyInstaller
```

---

## ⚙️ Requisitos previos
- Python 3.9+  
- MySQL Server  
- Node.js (opcional, solo si deseas procesar recursos de frontend)

Instalar dependencias:
```bash
pip install -r requirements.txt
```

---

## 📦 Dependencias principales
En `requirements.txt`:
```
pywebview
mysql-connector-python
python-dotenv
```

---

## 🗄️ Base de datos
La base de datos **MySQL** contendrá las siguientes tablas principales:

- **usuarios** (id, nombre, usuario, contraseña, rol)  
- **vehiculos** (id, placa, marca, modelo, cliente, fecha_registro)  
- **servicios** (id, nombre, precio)  
- **historial** (id, vehiculo_id, servicio_id, fecha, secretario_id)  
- **caja** (id, fecha, total_dia, secretario_id)  

---

## 🚀 Ejecución
```bash
python main.py
```

Esto abrirá la ventana del login. Según el rol, cargará el panel correspondiente.

---

## 📦 Empaquetado a .exe
Con PyInstaller:
```bash
pyinstaller --onefile --noconsole main.py
```

---

## 👨‍💻 Autores
Proyecto desarrollado como parte de la guía de **Sistema de Gestión de Lavadero**.
