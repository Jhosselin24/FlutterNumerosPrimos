# 🔢 Flutter Prime Counter
 
Una aplicación Flutter que muestra números primos de forma secuencial. Cada vez que presionas el botón, el contador avanza al siguiente número primo.
 
## ✨ Características
 
- Contador que salta automáticamente al siguiente número primo
- Interfaz limpia basada en Material Design
- Tema personalizado con colores vibrantes (rosa/fucsia)
- Botón flotante con ícono de corazón
- Soporte para Android y Web
## 📱 Capturas de pantalla
 
<img width="1293" height="979" alt="image" src="https://github.com/user-attachments/assets/ff0923a6-cdd7-4847-9aa7-3a6beab013d2" />
 
## 🚀 Instalación y ejecución
 
### Prerrequisitos
 
- [Flutter SDK](https://flutter.dev/docs/get-started/install)
- Android Studio o VS Code con extensión de Flutter
- Dispositivo Android o emulador
 
### Ejecutar en web
 
```bash
flutter run -d chrome
```
 
## 🧠 Lógica principal
 
La app arranca el contador en `1` y al presionar el botón busca el siguiente número primo usando el método `_esPrimo()`:
 
```dart
void _incrementCounter() {
  setState(() {
    _counter++;
    while (!_esPrimo(_counter)) {
      _counter++;
    }
  });
}
 
bool _esPrimo(int numero) {
  if (numero < 2) return false;
  for (int i = 2; i <= numero ~/ 2; i++) {
    if (numero % i == 0) return false;
  }
  return true;
}
```
 
La secuencia resultante es: **2 → 3 → 5 → 7 → 11 → 13 → ...**
 
## 🗂️ Estructura del proyecto
 
```
flutter_application_1/
├── lib/
│   └── main.dart          # Código principal de la app
├── android/               # Configuración nativa Android
├── web/                   # Configuración para web
│   ├── index.html
│   └── manifest.json
└── test/
    └── widget_test.dart   # Tests de widgets
```
 
## 🧪 Tests
 
```bash
flutter test
```
 
> ⚠️ Nota: el test por defecto del template asume que el contador inicia en `0`. Como esta app inicia en `1` y usa primos, los tests deben actualizarse acorde.
 
## 🛠️ Tecnologías
 
- [Flutter](https://flutter.dev/) — Framework UI multiplataforma
- [Dart](https://dart.dev/) — Lenguaje de programación
