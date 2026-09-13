# Expo + React Native + UI nativa + Tailwind


# Expo + React Native + UI nativa + Tailwind

La aplicación tiene una sola base de código, pero **no una sola estrategia visual ciega**.

Usaremos React Native/Expo para iOS y Android, React Native Web para web, y componentes nativos de Expo cuando aporten valor.

Expo UI ofrece componentes que conectan React con Jetpack Compose y SwiftUI, además de componentes universales. Para estilos, Tailwind puede usarse directamente en web y una capa de compatibilidad como NativeWind permite llevar el lenguaje de utilidades a React Native. citeturn0search0turn0search13turn0search9

## Regla de plataforma

```tsx
<View className="flex-1 p-4 web:max-w-3xl web:mx-auto">
  ...
</View>
```

No intentes que cada detalle visual sea idéntico.

Busca:

- misma semántica;
- misma jerarquía;
- misma información;
- controles apropiados a cada plataforma.

## Native UI

Para interacciones donde la plataforma importa:

```text
DatePicker
Switch
Context Menu
Navigation
Modal
Keyboard
Safe Area
```

prefiere componentes que respeten convenciones nativas.

## Tailwind

El objetivo no es llenar JSX de clases. El objetivo es que el estilo sea:

- consistente;
- fácil de revisar;
- portable;
- predecible.

Una buena extracción:

```tsx
const itemCard = "rounded-2xl border p-4 gap-2";
```

es preferible a repetir una cadena de 200 caracteres.

## Nota de actualidad

Las versiones de Expo/NativeWind evolucionan rápido. En el curso se evita fijar comandos irreversibles de instalación en las lecciones conceptuales; al iniciar el proyecto, consulta las instrucciones oficiales de la versión elegida.


## Ejercicio

Crea una pantalla de listado y marca qué elementos deben ser universales y cuáles deberían tener tratamiento específico para iOS, Android o web.
