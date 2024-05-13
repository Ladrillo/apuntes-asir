# Ejercicios de Grep con "El Quijote"

1. **Las Interminables Aventuras de un Ciertos Caballero**:
   - **Ejercicio**: Encuentra todas las líneas que mencionen "caballero".
   - **Comando**: `grep 'caballero' el_quijote.txt`

2. **En Busca de Dulcinea**:
   - **Ejercicio**: Encuentra todas las menciones de "Dulcinea" y cuéntalas.
   - **Comando**: `grep -c 'Dulcinea' el_quijote.txt`

3. **Las Desventuras de Sancho**:
   - **Ejercicio**: Encuentra todas las líneas donde "Sancho" habla, suponiendo que las líneas de diálogo incluyen un guión (-) después de su nombre.
   - **Comando**: `grep '- Sancho' el_quijote.txt`

4. **Palabras Sabias**:
   - **Ejercicio**: Extrae líneas que contengan cualquiera de "sabio", "prudente" o "astuto".
   - **Comando**: `grep -E 'sabio|prudente|astuto' el_quijote.txt`

5. **Búsqueda de Gigantes**:
   - **Ejercicio**: Identifica todas las descripciones de gigantes, que podrían estar disfrazados de "molinos" (molinos de viento).
   - **Comando**: `grep 'molinos' el_quijote.txt`

6. **Las Cicatrices de Batalla**:
   - **Ejercicio**: Encuentra líneas que describan lesiones o heridas, usando palabras como "herida" o "golpe".
   - **Comando**: `grep -E 'herida|golpe' el_quijote.txt`

7. **Amor Caballeresco**:
   - **Ejercicio**: Recupera líneas que mencionen "amor" seguido inmediatamente de "Dulcinea".
   - **Comando**: `grep 'amor.*Dulcinea' el_quijote.txt`

8. **Ecos de Risa**:
   - **Ejercicio**: Encuentra cualquier mención de risa, como "risa" o "reír".
   - **Comando**: `grep -E 'risa|reír' el_quijote.txt`

9. **Reflexiones sobre la Locura**:
   - **Ejercicio**: Busca líneas que cuestionen la cordura de Sancho o Don Quijote usando "loco" o "cuerdo".
   - **Comando**: `grep -E 'loco|cuerdo' el_quijote.txt`

10. **El Paisaje de La Mancha**:
    - **Ejercicio**: Extrae descripciones del entorno, buscando palabras como "campos", "cielo" o "tierra".
    - **Comando**: `grep -E 'campos|cielo|tierra' el_quijote.txt`

11. **Diálogos del Ingenioso Hidalgo**:

    - **Ejercicio**: Encuentra todas las líneas donde Don Quijote inicia un diálogo.

12. **Las Reflexiones del Narrador**:

    - **Ejercicio**: Busca pasajes donde el narrador ofrece reflexiones o comentarios directos al lector.

13. **Encuentros con la Nobleza**:

    - **Ejercicio**: Identifica todas las menciones de personajes con títulos nobiliarios como "duque", "marqués" o "rey".

14. **La Cocina en la Mancha**:

    - **Ejercicio**: Encuentra referencias a comidas o bebidas en la novela.

15. **Cabalgatas Solitarias**:

    - **Ejercicio**: Busca descripciones de Don Quijote cabalgando solo por el campo.

16. **Contrastes y Comparaciones**:

    - **Ejercicio**: Localiza las instancias donde se utilizan comparaciones o metáforas (pistas: busca palabras como "como" o "cual").

17. **Momentos de Desesperación**:

    - **Ejercicio**: Encuentra expresiones de tristeza o desesperación de los personajes principales.

18. **Encantamientos y Magia**:

    - **Ejercicio**: Busca todas las menciones de "encantamiento" o "magia" que reflejan las creencias de Don Quijote sobre su mundo.

19. **Animales en la Historia**:

    - **Ejercicio**: Identifica todas las líneas que mencionan animales, como "caballo", "burro" o "oveja".

20. **El Humor de Cervantes**:
    - **Ejercicio**: Encuentra líneas que contengan juegos de palabras o ironías, que son muy frecuentes en los diálogos entre Sancho y Don Quijote.
