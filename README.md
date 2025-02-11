# TELECOM CHURN

Una empresa de telecomunicaciones desea mejorar la retención de sus clientes, identificando aquellos que tienen más posibilidades de abandonar el servicio (Churn). Este proyecto tiene como objetivo limpiar y preparar un conjunto de datos para el entrenamiento de un modelo de Churn.

![image](https://github.com/user-attachments/assets/2d2488e0-febc-4002-9075-7cdd23a99674)

## 1. OBTENCIÓN Y CARGA DE LA DATA

![image](https://github.com/user-attachments/assets/af7b8f35-b420-4c41-91ff-a180a8375f5c)

![image](https://github.com/user-attachments/assets/2b5cf988-03c2-4eac-a778-01ce5679084e)

## 2. PREPROCESAMIENTO Y ANÁLISIS DE LA DATA
* Se visualizo como está distribuido nuestra variable objetivo con la finalidad de observar como podemos abordar el problema. Se observó que habían algunos valores que no representaban valor, se procedió a eliminarla.

![image](https://github.com/user-attachments/assets/d087b1f3-d35f-4fd7-929f-c6668df4f4ff)

* Obteniendo una nueva distribución en la variable objetivo.
  
![image](https://github.com/user-attachments/assets/9d00d3ef-601e-4879-a7e0-44f72f3ec478)

* El análisis de nulos fue un punto importante a tener en cuenta en el proyecto. Se realizaron visualizaciones con la finalidad de obtener mejores resultados. Se hizo practica de la imputación y eliminación de los valores nulos de acuerdo al análisis previo.

![image](https://github.com/user-attachments/assets/0248af3f-7a9d-4f08-b990-00fce052b47a)

![image](https://github.com/user-attachments/assets/b29fbbf7-d713-467f-9457-c04c6871d0a7)

* Luego de resolver el tema de los valores nulos, tuvimos que tratar el tema de los valores atípicos, que estuvieron presentes en algunas variables. Para esto se uso el análisis de percentiles en nuestra tabla descriptiva estadística.

![image](https://github.com/user-attachments/assets/93305de8-fe9e-44b1-b13d-185b2d015000)
![image](https://github.com/user-attachments/assets/905ecc59-2302-4470-92c1-8ed7c533142c)

* Otro aspecto importante en este punto, fue corregir el tipo de datos de las variables.

![image](https://github.com/user-attachments/assets/844a843e-bfee-44b2-a85d-047ea3aaa950)

* Algunas gráficas utilizadas para analizar nuestor dataframe.

![image](https://github.com/user-attachments/assets/7f38725b-6960-4ab0-b237-7276a450a6c1)

![image](https://github.com/user-attachments/assets/fcc6f4f7-f0c5-47aa-873a-520acc64a802)

![image](https://github.com/user-attachments/assets/6f95fbdd-c3b9-4ebe-98e3-5e237694f0fd)

![image](https://github.com/user-attachments/assets/d50719f0-bd1e-4eb0-b28d-5b672426bf2a)

![image](https://github.com/user-attachments/assets/581a2c47-21db-4642-9095-e1a8e00384a4)

![image](https://github.com/user-attachments/assets/150c3a7f-001c-431c-bff1-f2d7cd454151)

![image](https://github.com/user-attachments/assets/7f702630-23af-4c3c-a226-3b38cd5f7795)

## 3. NORMALIZACIÓN MÉTODO PROPIO , REDUCCIÓN DE DIMENSIONALIDAD Y FEATURE IMPORTANCES

## 3.1 MÉTODO PROPIO

![image](https://github.com/user-attachments/assets/ff24d69c-edf4-4b46-8cab-51d03604c45f)

## 3.2 MÉTODO DE GRÁFICAS

![image](https://github.com/user-attachments/assets/02b828f4-3901-4023-8c82-55def07f061d)

![image](https://github.com/user-attachments/assets/b97a54a8-9475-44bb-9e67-e1c674eef74a)

## 3.3 HEATMAP

![image](https://github.com/user-attachments/assets/ce414584-5c0f-4bdd-8ba4-7f365a3fb347)

Mapa de Calor de la Matriz de Correlación - Variables correlacionadas >70
![image](https://github.com/user-attachments/assets/34e29a18-caa4-42db-af41-0de0b6ac9115)

Después de eliminar las variables correlacionadas nos queda de esta manera. Si bien aún observamos cierta correlación entre variables, consideramos que son improtantes para nuestro modelo.
![image](https://github.com/user-attachments/assets/d02a400d-b2db-4e2a-a345-e03613ad6c81)

![image](https://github.com/user-attachments/assets/f61d2845-5a12-4255-9b62-df2f347d1771)

## 3.4 SELECTKBEST

![image](https://github.com/user-attachments/assets/b681d062-793b-47f9-9a64-09975191c1a3)

![image](https://github.com/user-attachments/assets/d762558a-5ad8-4701-b0c4-f936dbe084d3)


## 3.5 RFE (Recursive Feature Elimination)

![image](https://github.com/user-attachments/assets/c062c25e-b411-4dc5-bf97-d2e01c671467)

![image](https://github.com/user-attachments/assets/2dd195e8-9ca9-4954-831a-bb80cc358e81)

## 3.6 PCA (Principal Component Analysis)

![image](https://github.com/user-attachments/assets/43bfc38f-7b09-4339-bdb5-f0e7c5c16214)

## 4. COMPARACIÓN DE TÉCNICAS DE DATACLEANING

![image](https://github.com/user-attachments/assets/22eab390-45e6-49c6-a972-3d4ef6ba8529)

### 4.1 CONCLUSIONES

1. <ins>**Mejores Métricas para Data No Balanceada:**</ins> Se observó que las técnicas aplicadas dieron mejores resultados en la data sin balancear. Sin embargo, es importante considerar que en escenarios reales, donde el desbalanceo de clases puede influir en el sesgo del modelo, sería conveniente realizar pruebas adicionales con técnicas de balanceo de datos (como SMOTE o subsampling) para evaluar si se obtienen mejoras adicionales en las métricas, particularmente en datasets de menor tamaño.

2. <ins>**RFE**</ins>: Un Caso de Estudio para Compromisos: Si bien RFE presenta los mejores resultados en términos de accuracy (0.8101) y F1-Score (0.8012), su mayor costo en tiempo de entrenamiento (10.0477 segundos) lo convierte en una opción menos ideal para aplicaciones en tiempo real o con datasets más grandes. Esto indica que, aunque el rendimiento es superior, la escalabilidad de esta técnica debe evaluarse antes de su uso en producción.

3. <ins>**Análisis Manual:</ins>** Heatmap y Gráficos: A pesar de los tiempos de entrenamiento reducidos que ofrecen Heatmap y Gráficos, su dependencia de análisis manual puede limitar su aplicabilidad en entornos automatizados. Además, aunque el número de características es alto en ambos casos, los resultados métricos son aceptables, lo que sugiere que pueden ser opciones útiles en entornos donde el análisis rápido sea más importante que la precisión máxima.

4. <ins>**SelectKBest:**</ins> Balance Entre Métricas y Tiempo: SelectKBest parece ser una técnica intermedia, con un equilibrio razonable entre el número de características seleccionadas y los tiempos de entrenamiento. Su eficiencia en términos de tiempo lo posiciona como una opción viable en situaciones donde el tiempo es crítico, pero se requiere un número considerable de características para mantener la precisión. Sin embargo, sería interesante evaluar si se pueden optimizar aún más los parámetros del algoritmo para reducir el número de características sin sacrificar la precisión.

5. <ins>**PCA:**</ins> Eficiencia y Robustez: PCA emerge como la técnica más equilibrada, logrando reducir significativamente el número de características a 9, lo que es notablemente menor en comparación con las demás técnicas. Esto, sumado a tiempos de entrenamiento aceptables (1.7793 segundos) y métricas que superan el umbral del 80%, lo convierte en una opción sólida para entornos de desarrollo donde la eficiencia es una prioridad. No obstante, sería prudente validar este enfoque en un ambiente de pruebas más riguroso, sobre todo en tareas que requieran procesamiento de grandes volúmenes de datos o en aplicaciones en tiempo real.

6. <ins>**Selección de Modelos:**</ins> Si bien RFE proporciona las mejores métricas, el análisis sugiere que PCA y SelectKBest son los métodos más adecuados para llevar a producción por su equilibrio entre rendimiento y eficiencia. Se recomienda realizar pruebas adicionales en un entorno de desarrollo, considerando la carga de datos en tiempo real, para determinar la técnica más adecuada dependiendo de los requisitos específicos del sistema.

7. <ins>**Escalabilidad y Rendimiento en Producción:**</ins> Además de los resultados presentados, es fundamental realizar una evaluación del rendimiento de cada técnica en entornos de producción, especialmente considerando datasets más grandes y la posibilidad de ejecutar el modelo en servidores con recursos limitados.

8. <ins>**Aplicabilidad en Tiempo Real:**</ins> Las técnicas como RFE, aunque muestran excelentes métricas, deben someterse a pruebas adicionales para evaluar su aplicabilidad en aplicaciones en tiempo real, donde el tiempo de respuesta es crítico.

9. <ins>**Impacto de la Reducción de Características en el Modelo:**</ins> La reducción de características a través de PCA y SelectKBest es prometedora no solo por la mejora en tiempos de entrenamiento, sino también porque simplifica el modelo, lo que podría mejorar la interpretabilidad sin comprometer demasiado la precisión.

## 5. APLICACIÓN DE HIPERPARÁMETROS

Solo se aplicó a las dos técnicas que observamos que tuvieron mejores resultados, las cuales fueron SELECTKBEST y PCA

![image](https://github.com/user-attachments/assets/bbf4d8f5-48c5-479c-afe2-4af8c578921c)

![image](https://github.com/user-attachments/assets/aebaa241-1661-41f3-b855-4b6a13d1444c)

![image](https://github.com/user-attachments/assets/ef6986ae-861d-4e91-bd84-fc493eea197f)

### 5.1. CONCLUSIONES

1. <INS>**Alto Sobreajuste:**</INS> Ambos modelos, SelectKBest y PCA, presentan altos valores en las métricas de entrenamiento, mientras que en las métricas de prueba se observa una notable diferencia. Esto indica una posible tendencia al sobreajuste, donde los modelos están aprendiendo de manera más efectiva solo de los datos de entrenamiento, pero no se desempeñan bien con datos nuevos.

2. <INS>**Impacto de los Hiperparámetros:**</INS> Tras la aplicación de hiperparámetros, aunque las métricas absolutas no mostraron una mejora significativa, la diferencia entre los valores de las métricas de entrenamiento y prueba se redujo. Esto sugiere que se ha mejorado el sobreajuste, permitiendo que los modelos generalicen mejor a datos no vistos.

3. <INS>**Mejoras en el Rendimiento:**</INS> La optimización mediante hiperparámetros ha permitido una mejora en el rendimiento general de los modelos al reducir el riesgo de sobreajuste, lo que es un paso positivo hacia un modelo más robusto.

4. <INS>**Necesidad de Más Evaluación:**</INS> Para incrementar aún más los valores de las métricas, sería beneficioso recopilar más información o evaluar características adicionales. Esto podría ayudar a enriquecer el modelo y mejorar su capacidad de generalización.






























