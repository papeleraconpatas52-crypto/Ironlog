# IronLog – generar el APK

## Opción A: sin instalar nada (GitHub Actions)
1. Crea una cuenta en github.com y un repositorio nuevo (puede ser privado).
2. Sube TODO el contenido de esta carpeta (incluida la carpeta oculta .github).
3. Entra a la pestaña "Actions" > "Build APK" > "Run workflow".
4. Espera 4-6 minutos. Al terminar, abre la ejecución y descarga "IronLog-apk" (viene en un .zip con app-debug.apk).
5. Pasa el APK al celular, ábrelo y permite "instalar apps desconocidas" cuando Android lo pida.

## Opción B: en tu computadora
Requisitos: Node 18+, Java 17 y Android Studio (o el SDK de Android).
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
El APK queda en android/app/build/outputs/apk/debug/app-debug.apk

## Editar la app
Todo el código está en www/index.html. Después de cambiarlo, ejecuta "npx cap sync android" y vuelve a compilar.

## Notas
- Los datos se guardan dentro de la app, en el celular.
- La tipografía Sora se descarga de Google Fonts; sin internet se usa la fuente del sistema.
- Es un APK de depuración, válido para uso personal. Para Play Store hace falta uno firmado (release).
