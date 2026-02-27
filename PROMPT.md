## PROMPT

Crea una aplicación web usando **HTML, TailwindCSS y TypeScript (sin frameworks)** que funcione como una calculadora financiera de conversión de tasas de interés, equivalente a una hoja de Excel que convierte tasas nominales a tasas efectivas según su capitalización y forma.

### 🎯 Objetivo

Permitir al usuario ingresar una tasa nominal, su periodo, tipo de capitalización y forma (vencida o anticipada), y obtener:

* IP → Tasa periódica
* IV → Tasa vencida equivalente
* IE → Tasa efectiva equivalente en el periodo deseado

---

## 🧮 Reglas financieras a implementar

### Periodos posibles

| Nombre     | Código | Periodos por año |
| ---------- | ------ | ---------------- |
| Anual      | A      | 1                |
| Semestral  | S      | 2                |
| Trimestral | T      | 4                |
| Bimensual  | B      | 6                |
| Mensual    | M      | 12               |

---

### Cálculos

Sea:

* j = tasa nominal (decimal)
* m = capitalizaciones por año
* k = periodos del periodo efectivo deseado

#### Tasa periódica (IP)

```
IP = j / m
```

#### Si la tasa es anticipada (A), convertir a vencida:

```
IV = IP / (1 - IP)
```

Si ya es vencida (V):

```
IV = IP
```

#### Tasa efectiva equivalente para otro periodo

```
IE = (1 + IV)^(m / k) - 1
```

---

## 🖥️ Interfaz

Diseña una UI moderna con Tailwind:

### Inputs

* Porcentaje (input number)

* Tipo de tasa nominal (select):

  * Anual
  * Semestral
  * Trimestral
  * Bimensual
  * Mensual

* Capitalización (select):

  * A, S, T, B, M

* Forma (select):

  * V = Vencida
  * A = Anticipada

* Periodo efectivo deseado (select):

  * Anual
  * Semestral
  * Trimestral
  * Bimensual
  * Mensual

### Botón

👉 **Calcular**

---

## 📊 Resultados (mostrar en tarjetas)

* IP (Tasa periódica)
* IV (Tasa vencida)
* IE (Tasa efectiva equivalente)
* Nombre del resultado (ej: "Efectivo Anual")

Mostrar valores con 4 decimales.

---

## 🎨 Diseño

* TailwindCSS
* Centrado vertical
* Tarjetas con sombra
* Responsive
* Modo oscuro

---

## 🧠 Lógica en TypeScript

* Separar funciones:

  * obtenerPeriodosPorCodigo()
  * calcularIP()
  * convertirAVencida()
  * calcularEfectiva()

---

## 📁 Estructura

```
index.html + Tailwind
app.ts
```

Compilar TypeScript a JavaScript.

---

## ⭐ Extras

* Validar inputs
* Permitir múltiples cálculos en una tabla historial
* Botón limpiar

