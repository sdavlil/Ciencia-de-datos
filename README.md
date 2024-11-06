# Visualizacion

import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# Cargar el dataset de Iris desde Seaborn
iris = sns.load_dataset('iris')

# Gráfico de Dispersión:

plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.scatter(iris['sepal_length'], iris['sepal_width'], c='blue', label='Sepal')
plt.xlabel('Sepal Length')
plt.ylabel('Sepal Width')
plt.title('Scatter Plot: Sepal Length vs Sepal Width')

plt.subplot(1, 2, 2)
plt.scatter(iris['petal_length'], iris['petal_width'], c='green', label='Petal')
plt.xlabel('Petal Length')
plt.ylabel('Petal Width')
plt.title('Scatter Plot: Petal Length vs Petal Width')
plt.show()

# Gráfico de Distribución:

plt.figure(figsize=(10, 8))
for i, column in enumerate(iris.columns[:-1], 1):
    plt.subplot(2, 2, i)
    plt.hist(iris[column], bins=15, color='skyblue', edgecolor='black')
    plt.title(f'Distribution of {column}')
plt.tight_layout()
plt.show()

# Gráfico de Pares:
sns.pairplot(iris, hue="species", markers=["o", "s", "D"])
plt.show()

# Mapa de Calor:
# Seleccionar solo las columnas numéricas
iris_numeric = iris.select_dtypes(include=['float64', 'int64'])

# Crear el mapa de calor de correlación
plt.figure(figsize=(8, 6))
sns.heatmap(iris_numeric.corr(), annot=True, cmap='coolwarm', linewidths=0.5)
plt.title('Correlation Heatmap of Iris Features')
plt.show()

Comparar la visualización de datos en Ciencia de Datos vs. Big Data usando el Dataset de Titanic
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Cargar el dataset de Titanic desde un archivo local
titanic = pd.read_csv('/content/Titanic.csv')

# Supervivencia por Clase

plt.figure(figsize=(8, 6))
sns.countplot(x='Pclass', hue='Survived', data=titanic, palette='viridis')
plt.title('Survival by Passenger Class')
plt.xlabel('Class')
plt.ylabel('Count')
plt.legend(['Not Survived', 'Survived'])
plt.show()

# Supervivencia por Edad

plt.figure(figsize=(10, 6))
sns.histplot(titanic, x='Age', hue='Survived', kde=True, multiple='stack', palette='coolwarm')
plt.title('Age Distribution by Survival Status')
plt.xlabel('Age')
plt.ylabel('Count')
plt.show()

# Supervivencia por Género y Clase

plt.figure(figsize=(8, 6))
sns.catplot(x="Sex", hue="Survived", col="Pclass", data=titanic, kind="count", height=4, aspect=0.7, palette="Set2")
plt.suptitle('Survival by Gender and Class')
plt.show()

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Ciencia-de-datos
Avance en el Proyecto sobre un Problema de Optimización

Descripción

Este informe presenta el avance del proyecto titulado "Optimización de la Asignación de Personal Técnico en la Mesa de Ayuda con Integración de un Chatbot". Este proyecto aborda el problema de los largos tiempos de espera y la sobrecarga en el personal técnico en las mesas de ayuda, donde el 60% de las solicitudes son problemas simples que podrían ser resueltos automáticamente.

Actividad

Cada grupo o estudiante presentará un informe que incluye los siguientes elementos:

•	Problema de Optimización Elegido: La optimización en la gestión del soporte técnico mediante la integración de un chatbot con inteligencia artificial para resolver problemas simples en la mesa de ayuda, lo que busca reducir los tiempos de espera y mejorar la eficiencia en la asignación del personal técnico.
•	Metodología Utilizada: Se ha seguido una metodología que incluye la identificación de problemas comunes en la mesa de ayuda, el análisis de los tiempos de espera y la satisfacción del usuario. Se ha diseñado un prototipo del chatbot y se están realizando pruebas en la plataforma GLPI para medir su efectividad en la resolución de problemas simples y en la optimización de la asignación de técnicos.
•	Resultados Preliminares: Hasta el momento, se ha logrado identificar los principales tipos de problemas que enfrenta la mesa de ayuda y se ha establecido un marco para la implementación del chatbot. Las pruebas iniciales indican que el chatbot tiene el potencial de resolver hasta el 40% de los problemas simples, lo que podría reducir significativamente los tiempos de espera y mejorar la satisfacción del usuario. Se están recopilando métricas sobre la eficiencia operativa y se prevé que se realicen más pruebas para evaluar el impacto en la carga de trabajo del personal técnico.

Avance en el Proyecto sobre Visualización de Datos

Descripción del Proyecto:

El proyecto "Optimización de la Asignación de Personal Técnico en la Mesa de Ayuda con Integración de un Chatbot" no solo busca mejorar la eficiencia operativa mediante un chatbot, sino también optimizar el análisis de los datos generados por la mesa de ayuda para una toma de decisiones más informada. En esta etapa, se ha comenzado a trabajar en la visualización de datos que nos permitan monitorear y evaluar la eficiencia del sistema en tiempo real. A través de la visualización de datos, se facilita la interpretación de métricas clave como los tiempos de espera, la carga de trabajo de los técnicos y el rendimiento del chatbot.

Métodos y Técnicas Utilizadas:
1.	Herramientas de Visualización:
o	Python (Matplotlib, Seaborn, y Pandas): Para la visualización y análisis de los datos relacionados con los tiempos de espera y la eficiencia del chatbot en la plataforma GLPI.
o	GLPI Metrics Dashboard: Se ha integrado el sistema GLPI con herramientas de visualización para extraer datos clave como el tiempo de resolución, número de tickets resueltos por el chatbot, y carga de trabajo de los técnicos.

3.	Métodos de Análisis de Datos:
o	Análisis Descriptivo: Se utilizaron técnicas de análisis descriptivo para examinar las métricas de rendimiento del chatbot, como el porcentaje de problemas simples resueltos y la reducción de los tiempos de espera.
o	Comparación de Métricas Pre y Post Implementación: Comparando los tiempos de resolución de tickets antes y después de la implementación del chatbot, se busca identificar mejoras significativas en la eficiencia.

5.	Técnicas de Visualización:
o	Gráficos de Barras y Líneas: Se utilizaron gráficos de barras para comparar la cantidad de tickets resueltos manualmente versus los resueltos automáticamente por el chatbot. Los gráficos de líneas ayudan a visualizar las tendencias en la reducción de los tiempos de espera a lo largo del tiempo.
o	Mapas de Calor: Se implementaron mapas de calor para identificar patrones en los tipos de solicitudes más frecuentes y los tiempos de resolución asociados, facilitando la identificación de cuellos de botella.

o	Gráficos de Distribución (Histograma y Boxplot): Para analizar la variabilidad de los tiempos de espera antes y después de la intervención del chatbot.
Resultados Obtenidos:

1.	Reducción de Tiempos de Espera: La visualización de los datos ha revelado una disminución significativa en los tiempos de espera de los tickets simples después de la implementación del chatbot. Los gráficos de líneas muestran una tendencia decreciente en los tiempos de espera, destacando que los problemas simples son resueltos más rápido por el chatbot.
   
3.	Eficiencia del Chatbot: Los resultados preliminares indican que el chatbot está resolviendo hasta un 40% de los problemas simples, lo que ha sido confirmado por los gráficos de barras. Esto sugiere que la integración del chatbot no solo está reduciendo los tiempos de espera, sino también aliviando la carga de trabajo del personal técnico.
   
5.	Optimización en la Asignación de Personal Técnico: Los mapas de calor mostraron que los técnicos están recibiendo más tickets complejos, ya que el chatbot se ocupa de los más simples. Esto se refleja en una mejora en la eficiencia de la asignación del personal técnico, donde se observa una disminución en el tiempo promedio que un técnico tarda en resolver un ticket complejo.
   
7.	Impacto en la Satisfacción del Usuario: Aunque los datos sobre la satisfacción del usuario aún se están recopilando, los primeros resultados sugieren que la mejora en los tiempos de respuesta y la resolución automática de problemas simples están teniendo un impacto positivo en la percepción del servicio.
