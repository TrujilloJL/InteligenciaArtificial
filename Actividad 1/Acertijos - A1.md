# Acertijos

  

## 1. El Problema de los 3 Monjes y 3 Caníbales

### Planteamiento y Reglas

Tres monjes ($M$) y tres caníbales ($C$) deben cruzar un río usando una lancha con capacidad de 2 personas.

* La barca requiere al menos 1 persona para remar y máximo 2.
* En ninguna orilla los caníbales pueden superar en número a los monjes.
* **Objetivo:** Cruzar a todos los monjes y caníbales a la otra orilla.

**Solución:**

{C} {C} {C} {M} {M} {M} → _ → {}{}{}{}{}{}

{C} {} {} {M} {M} {M} → _{C}{C} → {}{}{}{}{}{} - Viajan dos caníbales

{C} {} {} {M} {M} {M} → _{C}{} → {C}{}{}{}{}{} - Regresa un caníbal

{} {} {} {M} {M} {M} → _{C}{C} → {C}{}{}{}{}{} - Viajan dos caníbales

{C} {} {} {M} {M} {M} → _{C}{} → {C}{C}{}{}{}{} - Regresa un caníbal

{C} {} {} {M} {} {} → _{M}{M} → {C}{C}{}{}{}{} - Viajan dos monjes

{C} {C} {} {M} {M} {} → _{C}{M} → {C}{}{}{M}{}{} - Regresan un caníbal y un monje

{C} {C} {} {} {} {} → _{M}{M} → {C}{}{}{M}{}{} - Viajan dos monjes

{C} {C} {C} {} {} {} → _{C}{} → {}{}{}{M}{M}{M} - Regresa un caníbal

{C} {} {} {} {} {} → _{C}{C} → {}{}{}{M}{M}{M} - Viajan dos caníbales

{C} {C} {} {} {} {} → _{C}{} → {C}{}{}{M}{M}{M} - Regresa un caníbal

{} {} {} {} {} {} → _{C}{C} → {C}{}{}{M}{M}{M} - Viajan dos caníbales

{} {} {} {} {} {} → _ → {C}{C}{C}{M}{M}{M} - Todos cruzaron a salvo

---
## 2. Laberinto

### Planteamiento
Encontrar una ruta óptima desde una casilla de inicio hasta una meta y que funcione para cualquier laberinto

**Solución**
1. Para iniciar mete la celda de inicio a la cola y se marca como visitada.
2. Extrae la celda actual de la cola.
3. Si la celda actual es la salida, detén la búsqueda y usa tus anotaciones de origen para trazar la ruta final.
4. Para avanzar, mira sus 4 lados (Arriba, Abajo, Izquierda, Derecha).
5. Si no es pared y no ha sido visitada, regístrala como visitada, anota de qué celda proviene y se pone en la cola. Y así sucesivamente hasta llegar al final

---
