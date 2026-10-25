# Apocalypse Plus (Forge 1.20.1)

Mod para apocalipsis zombi. Incluye:

- Contador de días y hordas que crecen cada noche (horda grande cada 7 días)
- Zombis especiales: corredor, gigante, explosivo y ácido
- Ruido que atrae zombis: disparos, romper bloques, puertas/cofres y explosiones
- Eventos aleatorios: caída de suministros, tormenta de niebla y superviviente que pide ayuda
- Niebla constante que no deja ver el borde de los chunks (solo cliente)

## Cómo compilarlo

1. Instala **JDK 17** y un IDE (IntelliJ IDEA Community o Eclipse).
2. Descarga el **Forge MDK 1.20.1** (47.x) desde https://files.minecraftforge.net y descomprímelo.
3. Dentro del MDK, borra la carpeta `src/main/java/com/example` (el ejemplo) y el archivo
   `src/main/resources/META-INF/mods.toml` original.
4. Copia la carpeta `src` de este proyecto dentro del MDK (acepta reemplazar).
5. En `gradle.properties` del MDK pon: `mod_id=apocalypse_plus`
6. En una terminal, dentro del MDK: `gradlew build` (en Windows) o `./gradlew build`.
7. El mod queda en `build/libs/`. Cópialo a la carpeta `mods` de tu instancia 1.20.1 con Forge.

Si el build da errores, copia el mensaje completo del error y se corrige.

## Configuración

Se generan al abrir el juego:

- `config/apocalypse_plus-common.toml`: hordas, zombis especiales, ruido y eventos
- `config/apocalypse_plus-client.toml`: niebla (distancia, color, brillo)

## Notas

- Los disparos se detectan por el **nombre del sonido** de otros mods (palabras como shoot, gun, rifle).
  Si un mod de armas no atrae zombis, agrega una palabra en `palabrasDeDisparo`.
- Los zombis "gigantes" tienen más vida y daño, pero no son más grandes (eso requiere un renderizador propio).
- Con shaders activados (Oculus/Iris) la niebla la controla el shader y la del mod no se aplica.
