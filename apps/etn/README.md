# MaestroAPPSaaS

Proyecto de automatización E2E para aplicaciones móviles SaaS usando Maestro Framework.

## 🚀 Aplicaciones soportadas

- **ETN Turistar Lujo** (`mx.com.etn.etnturistarlujo`) - App de reserva de boletos de autobús
- **PrimeraPlus** (`com.gfa.PrimeraPlus`) - App de transporte y reservas

## 📁 Estructura del proyecto

```
MaestroAPPSaaS/
├── apps/
│   ├── etn/                    # Tests para ETN Turistar Lujo
│   │   ├── .maestro/flows/     # Flows de ETN
│   │   ├── screenshots/        # Evidencia de ETN
│   │   ├── package.json        # Scripts de ETN
│   │   └── README.md           # Documentación ETN
│   └── primeraplus/            # Tests para PrimeraPlus
│       ├── .maestro/flows/     # Flows de PrimeraPlus
│       ├── screenshots/        # Evidencia de PrimeraPlus
│       ├── package.json        # Scripts de PrimeraPlus
│       └── README.md           # Documentación PrimeraPlus
├── shared/                     # Utilidades compartidas
├── .gitignore                  # Archivos a ignorar
└── README.md                   # Esta documentación
```

## 🛠️ Prerequisitos

- [Maestro CLI](https://maestro.mobile.dev/) - Framework de testing E2E
- Android Studio con SDK configurado
- Emulador Android o dispositivo físico
- Node.js (para scripts de automatización)

## 📱 Configuración inicial

### 1. Instalar Maestro
```bash
curl -Ls "https://get.maestro.mobile.dev" | bash
```

### 2. Configurar Android SDK
```bash
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

### 3. Iniciar emulador
```bash
emulator -avd Pixel_7_API_35 &
adb devices
```

## 🧪 Ejecutar tests

### Para ETN Turistar Lujo:
```bash
cd apps/etn
npm run app:open        # Abrir ETN
npm run test:smoke      # Test básico
npm run test:booking    # Flujo completo de reserva
```

### Para PrimeraPlus:
```bash
cd apps/primeraplus
npm run app:open        # Abrir PrimeraPlus
npm run test:smoke      # Test básico
npm run test:booking    # Flujo completo de reserva
```

## 🔧 Comandos útiles

### Debugging
```bash
maestro hierarchy       # Ver elementos en pantalla
maestro studio          # Interfaz visual de debugging
maestro record          # Grabar sesión interactiva
```

### Desarrollo
```bash
maestro test --continuous flow.yaml    # Modo watch
maestro test --verbose flow.yaml       # Logs detallados
maestro test --delay 2000 flow.yaml    # Ejecutar con delay
```

## 📊 Tipos de tests

### Básicos (Smoke Tests)
- Verificar que la app se abre
- Navegación básica
- Elementos principales visibles

### Funcionales
- Búsqueda de rutas
- Selección de destinos
- Navegación entre pantallas

### Críticos (E2E)
- Flujo completo de reserva
- Llenado de formularios
- Proceso de pago (hasta confirmación)

## 🏗️ Arquitectura

Cada aplicación tiene su propio entorno independiente:

- **Flows separados**: Cada app tiene sus propios archivos .yaml
- **Screenshots independientes**: Evidencia organizada por app
- **Scripts específicos**: package.json personalizado por app
- **Documentación individual**: README específico por app

## 🤝 Contribuir

1. Fork el proyecto
2. Crear rama para nueva feature (`git checkout -b feature/nueva-app`)
3. Commit cambios (`git commit -am 'Agregar tests para nueva app'`)
4. Push a la rama (`git push origin feature/nueva-app`)
5. Crear Pull Request

## 📝 Notas

- Las apps usan la plataforma Reservamos (`com.reservamossaas.app.MainActivity`)
- Se utilizan datos de prueba seguros
- Screenshots se guardan como evidencia
- Flows están optimizados para estabilidad

## 🔗 Enlaces útiles

- [Documentación Maestro](https://maestro.mobile.dev/)
- [Maestro GitHub](https://github.com/mobile-dev-inc/maestro)
- [Guía de mejores prácticas](https://maestro.mobile.dev/best-practices)

---

**Desarrollado con ❤️ usando Maestro Framework**