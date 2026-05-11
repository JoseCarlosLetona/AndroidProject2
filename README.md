# 📱 Proyecto Android - Multi-idioma y Multi-pantalla

Proyecto Android completo con soporte para 4 idiomas y adaptación a múltiples pantallas/orientaciones.

## ✨ Características

- 🌍 **4 idiomas**: Español (default), Inglés, Francés, Alemán
- 📐 **Layouts adaptables**: Portrait y Landscape
- 🖼️ **Fondo nine-patch**: Redimensionable sin deformar el marcianito
- 📱 **Multi-pantalla**: Funciona en cualquier tamaño y orientación

## 🚀 Cómo usar

### Opción 1: Android Studio (Recomendado)
1. Descarga y descomprime este ZIP
2. Abre **Android Studio**
3. Selecciona **"Open an existing project"**
4. Navega a la carpeta `AndroidProject`
5. Espera a que Gradle sincronice (puede tardar unos minutos la primera vez)
6. Conecta un dispositivo o inicia un emulador
7. Click en **Run** ▶️

### Opción 2: Línea de comandos
```bash
cd AndroidProject
./gradlew assembleDebug
```

## ⚠️ Importante: Nine-Patch

El archivo **`background.9.png` NO está incluido**. Debes crearlo manualmente:

1. Toma la imagen original del ejercicio (fondo azul con marcianito y nubes)
2. En Android Studio: Click derecho en `app/src/main/res/drawable/` → **New** → **Drawable Resource File**
3. O usa la herramienta **draw9patch** del Android SDK
4. Marca las zonas de estiramiento:
   - **Estirar**: Solo las zonas del degradado azul
   - **Proteger**: El marcianito Android y las nubes (no deben deformarse)
5. Guarda como `background.9.png` en `app/src/main/res/drawable/`

### Guía rápida del Nine-Patch

```
Borde superior:    ████████████████████████████████  (estirar todo excepto centro)
Borde izquierdo:   ████                            (estirar solo zona superior)
                   ████
                   ████
                   ░░░░  <- robot (NO estirar)
                   ░░░░
                   ████
                   ████
Borde inferior:   ████████████████████████████████  (área de contenido)
Borde derecho:    ████                            (padding)
```

## 📁 Estructura del proyecto

```
AndroidProject/
├── .gitignore
├── build.gradle.kts
├── settings.gradle.kts
├── gradle.properties
├── gradlew / gradlew.bat
├── gradle/wrapper/
└── app/
    ├── build.gradle.kts
    ├── proguard-rules.pro
    └── src/main/
        ├── AndroidManifest.xml
        ├── java/com/example/androidproject/
        │   └── MainActivity.kt
        └── res/
            ├── drawable/
            │   ├── ic_android.xml
            │   └── background.9.png  ← CREAR MANUALMENTE
            ├── layout/
            │   └── activity_main.xml
            ├── layout-land/
            │   └── activity_main.xml
            ├── values/           ← Español (default)
            ├── values-en/        ← Inglés
            ├── values-fr/        ← Francés
            └── values-de/        ← Alemán
```

## 🐛 Solución de problemas

| Problema | Solución |
|----------|----------|
| "Gradle sync failed" | Verifica que tienes Java 17+ instalado |
| "SDK not found" | Configura `local.properties` con tu ruta del SDK |
| "background.9.png not found" | Crea el archivo nine-patch manualmente |
| Emulador lento | Habilita aceleración por hardware (HAXM/Hyper-V) |

## 📋 Requisitos

- Android Studio Hedgehog (2023.1.1) o superior
- JDK 17 o superior
- Android SDK API 34
- Gradle 8.2

## 📝 Nota para GitHub

Este proyecto está listo para subir a GitHub. Solo ejecuta:

```bash
cd AndroidProject
git init
git add .
git commit -m "Initial commit: Android multi-language project"
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main
```

> ⚠️ **No subas `local.properties`** — ya está incluido en `.gitignore`

---

Hecho con ❤️ para el ejercicio de Android
