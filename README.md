## Introducción

### Nombre del proyecto

**Optimización de la Experiencia del Viajero con IA**

### Problema a abordar

Planificar un viaje puede ser complicado y consumir mucho tiempo, ya que la información sobre destinos, clima y vestimenta adecuada suele estar dispersa en múltiples fuentes. Muchos viajeros enfrentan dificultades para organizar su itinerario, elegir la ropa adecuada para el clima del destino y optimizar su tiempo en el lugar visitado.

Este problema es relevante porque una mala planificación puede generar experiencias insatisfactorias, gastos innecesarios y dificultades durante el viaje. Por ello, contar con una herramienta que centralice y personalice la información puede mejorar significativamente la experiencia del viajero.

---

## Propuesta de solución

Crear una herramienta basada en inteligencia artificial que ofrezca recomendaciones personalizadas a partir de la información proporcionada por el usuario.

La solución se vincula con el desarrollo de modelos de IA al emplear técnicas de procesamiento de lenguaje natural (NLP) para generar respuestas precisas y relevantes. Además, se usarán modelos de generación de imágenes para ilustrar las recomendaciones de vestimenta en función del clima.

Los **prompts** utilizados permitirán obtener:

- **Lugares turísticos recomendados** en el destino elegido.
- **Pronóstico del clima** para el período de viaje.
- **Recomendaciones de vestimenta** con generación de imágenes para facilitar la planificación.

### Ejemplo de prompts

#### Texto a texto:

```
Actúa como un asistente de viajes experto. El usuario planea un viaje a [Destino] desde [Fecha de Inicio] hasta [Fecha de Fin]. Tu tarea es:

1. Sugerir cinco lugares de interés turístico en [Destino].
2. Describir el clima esperado durante ese período.
3. Recomendar el tipo de ropa y accesorios adecuados según las condiciones climáticas.

Proporciona una respuesta clara y organizada en una lista con viñetas. Usa un tono experto y amigable para orientar al viajero.
```

#### Texto a imagen:

```
Genera una imagen que represente la ropa ideal para un viaje a [Destino] durante el período de [Fecha de Inicio] a [Fecha de Fin], basada en un clima [Condiciones Climáticas].

El atuendo debe ser cómodo, moderno y apropiado para hacer turismo. Incluye accesorios como gafas de sol o paraguas, dependiendo del clima. Usa un fondo sencillo para resaltar la vestimenta.
```

---

## Justificación de la viabilidad del proyecto

- **Tiempo:** Desarrollo estimado entre 4 y 6 semanas.
- **Recursos:** Uso de modelos de IA (ChatGPT y DALL·E) y fuentes de datos abiertos sobre clima y turismo.
- **Factibilidad Técnica:** La combinación de generación de texto e imágenes es viable con las tecnologías actuales, lo que permite una implementación efectiva.

---

## Objetivos

1. Desarrollar una herramienta que facilite la planificación de viajes mediante IA.
2. Generar recomendaciones personalizadas basadas en destino y clima.
3. Mejorar la experiencia del usuario mediante generación de imágenes de vestimenta recomendada.

---

## Metodología

Para alcanzar los objetivos, se seguirán los siguientes procedimientos:

- Implementación de modelos de IA para extraer información de sitios turísticos y condiciones climáticas.
- Creación de prompts optimizados para mejorar la calidad de las respuestas generadas.
- Integración de un modelo de generación de imágenes para mostrar atuendos recomendados.
- Evaluación y mejora del sistema a través de pruebas iterativas.

---

## Herramientas y tecnologías

Se emplearán las siguientes técnicas y herramientas:

- **Fast Prompting**: Aplicación de técnicas avanzadas de optimización de prompts para obtener respuestas más precisas y relevantes en menor tiempo.
- **Modelos de lenguaje**: ChatGPT para la generación de respuestas textuales.
- **Generación de imágenes**: DALL·E/NightCafe para la creación de ilustraciones de vestimenta.
- **Fuentes de datos**: APIs de clima y turismo.

Justificación:

- **Fast Prompting** permite mejorar la eficiencia en la generación de respuestas mediante el ajuste y refinamiento iterativo de los prompts.
- **Experimentación con diferentes configuraciones de prompts** para optimizar la eficacia de la IA en la entrega de información relevante.
- La combinación de generación de texto e imágenes facilita una mejor comprensión de la información.

---

## Implementación

### Prompt y código

Se desarrollará un prototipo utilizando Python y las APIs de OpenAI:

#### **Ejemplo de código en python**

```python
import openai

def obtener_recomendaciones_viaje(destino, fecha_inicio, fecha_fin):
    prompt = f"""
    Actúa como un asistente de viajes experto. El usuario planea un viaje a {destino} desde {fecha_inicio} hasta {fecha_fin}.
    1. Sugerir cinco lugares de interés turístico.
    2. Describir el clima esperado.
    3. Recomendar el tipo de ropa adecuada.
    """

    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "system", "content": prompt}]
    )

    return response["choices"][0]["message"]["content"]

# Ejemplo de uso
print(obtener_recomendaciones_viaje("Buenos Aires", "2024-03-20", "2024-03-27"))
```

Este código genera automáticamente las recomendaciones de viaje basadas en el destino y fechas ingresadas.

---
