# An-lisis-de-datos-para-la-empresa-Mint-Classics.SQL
Este análisis profundiza en los datos operativos, de ventas y de inventario de Mint Classics, una empresa especializada en modelos de automóviles. El objetivo principal era optimizar las ventas de productos, la gestión de inventario y la eficiencia del almacén para maximizar la rentabilidad y la eficacia operativa

[Análisis de datos para la empresa Mint Classics.SQL.pdf](https://github.com/user-attachments/files/17440664/Analisis.de.datos.para.la.empresa.Mint.Classics.SQL.pdf)

[Descubriendo información sobre inventarios mint classec 22.docx](https://github.com/user-attachments/files/17441054/Descubriendo.informacion.sobre.inventarios.mint.classec.22.docx)

Análisis de datos para la empresa Mint Classics 

Objetivos 
• Análisis de ventas de productos: Productos identificados que se venden más y de bajo 
rendimiento para elaborar estrategias para maximizar las ganancias. 
• Gestión de inventario y almacén: Exploró las co-ocurrencias de productos para optimizar la 
colocación de productos y mejorar la eficiencia del almacén. 
• Evaluación de la rentabilidad: Evaluó los márgenes de beneficio y recomendó estrategias 
para aumentar la rentabilidad de los artículos populares. 
• Análisis de eficiencia del almacén: Tasas de rotación de inventario evaluadas en todos los 
almacenes para identificar disparidades de eficiencia. 
Principales conclusiones: 

• Ventas de productos y rentabilidad: Descubrí los productos más y menos populares y 
recomendé descontinuar los artículos de bajo rendimiento. Áreas de crecimiento de 
ganancias identificadas mediante la auditoría de productos de altas ventas, bajos 
márgenes de ganancia. 
• Optimización del almacén: Se sugiere almacenar juntos los productos comúnmente 
pedidos y reorganizar los diseños del almacén para aumentar la eficiencia. 
• Eficiencia del almacén: Se destacaron las disparidades en el rendimiento del almacén, se 
recomendó estudiar modelos de almacén exitosos y una posible consolidación para la 
optimización de costos. 
Recomendaciones: 
• Descontinuar productos de bajo rendimiento: Descontinuar el Toyota Supra debido a cero 
ventas, optimizando el inventario y reduciendo costos. 
• Maximice las ganancias en artículos populares: Audite productos con altas ventas y baja 
rentabilidad para aumentar los márgenes de ganancia. 
• Optimice las operaciones de almacén: almacene juntos los productos pedidos con 
frecuencia, reorganice los almacenes y estudie modelos de almacén eficientes para su 
implementación. 
• Investigue la eficiencia del almacén sur: estudie el modelo exitoso de almacén sur para 
obtener información sobre cómo mejorar el almacén oeste menos eficiente o consolidar 
potencialmente los almacenes para ahorrar costos. 
Limitaciones y consideraciones futuras 
• Limitaciones de los datos: El acceso limitado a la dinámica detallada del inventario del 
almacén restringió la comprensión más profunda de la gestión del inventario. 
• Exploración adicional: segmentación de clientes sugerida, análisis predictivo y análisis de la 
cesta de la compra para optimizar las operaciones dentro del mercado de EE. UU. 
Conclusión 
Este análisis proporciona recomendaciones prácticas para mejorar la eficiencia operativa de Mint 
Classics, aumentar la rentabilidad y agilizar las operaciones de almacén. Las estrategias sugeridas 
t
 ienen como objetivo mejorar las ventas, reducir costos y optimizar recursos, asegurando un 
modelo de negocio más efectivo y competitivo. 
Introducción 
The Mint Classics Company (MC) es una empresa completamente inventada que vende modelos 
de coches. La empresa se enfrenta al reto de optimizar su inventario en múltiples instalaciones de 
almacenamiento. 
Como parte de su iniciativa estratégica para mejorar la eficiencia operativa, MC tiene como 
objetivo explorar sus datos de inventario actuales y obtener información que pueda guiar las 
decisiones sobre la reorganización o reducción del inventario. La compañía también quiere 
identificar áreas de oportunidad para aumentar las ganancias generales. 
Este proyecto profundiza en un análisis exploratorio de datos (EDA) de la base de datos MC, 
examinando varias facetas de la gestión de inventario, las correlaciones de ventas y la utilización 
del almacén. 
Al aprovechar las consultas SQL en el esquema de base de datos proporcionado, este análisis busca 
identificar patrones, descubrir relaciones entre el inventario y las cifras de ventas, y recomendar 
acciones potenciales para optimizar el inventario al tiempo que se garantiza un servicio oportuno a 
los clientes. 
Conclusión clave: ¡Soy un analista real que ayuda a una empresa falsa a resolver un problema falso 
para demostrarle mi capacidad para usar SQL! 
Objetivos del proyecto 
1. Explore los datos: Demuestre una comprensión de los datos que están disponibles y 
comprenda mejor a la empresa Mint Classics. 
2. Análisis de ventas: Explora las ventas de productos. 
3. Evaluación de la eficiencia del almacén: Analice las capacidades del almacén y sugiera 
posibles estrategias de consolidación. 
A través de esta exploración, el proyecto tiene como objetivo ofrecer recomendaciones prácticas 
basadas en datos que puedan ayudar a Mint Classics a tomar decisiones informadas para optimizar 
sus prácticas de gestión de inventario. Quién sabe, ¡tal vez incluso cerremos uno o dos almacenes! 
Sin embargo, no hay promesas. 
Descripción de los datos 
Los datos de este proyecto provienen de Coursera. 
Para ayudar en este proyecto se utilizaron las siguientes herramientas: 
• MySQL Workbench 
• Hojas de cálculo de Google 
Esquema de base de datos 
El proyecto utiliza una base de datos MySQL con el siguiente esquema: 
Mesas 
1. customers: Contiene información sobre los clientes. 
o Clave principal: customerNumber 
2. employees: Almacena los datos de los empleados de la empresa. 
o Clave principal: employeeNumber 
3. oficinas: Contiene datos relacionados con las oficinas y ubicaciones de la empresa. 
o Clave principal: officeCode 
4. pedidos: incluye detalles del pedido, como el número de pedido, la fecha y el estado. 
o Clave principal: orderNumber 
o Clave foránea: (tabla de referencias)customerNumbercustomers 
5. orderdetails: Almacena información específica sobre cada elemento de línea de pedido. 
o Clave principal compuesta: (, orderNumberproductCode) 
o Clave foránea: (tabla de referencias)orderNumberorders 
o Clave foránea: (tabla de referencias)productCodeproducts 
6. pagos: Contiene información de pago de los clientes. 
o Clave principal compuesta: (, customerNumbercheckNumber) 
o Clave foránea: (tabla de referencias)customerNumbercustomers 
7. líneas de productos: Almacena diferentes líneas de productos y descripciones. 
o Clave principal: productLine 
8. productos: Contiene información sobre varios productos disponibles. 
o Clave principal: productCode 
o Clave foránea: (tabla de referencias)productLineproductlines 
o Clave foránea: (tabla de referencias)warehouseCodewarehouses 
9. almacenes: Contiene datos sobre diferentes instalaciones de almacenamiento. 
o Clave principal: warehouseCode 
Paso 1: importar el archivo SQL en SQL Workbench 
en este paso inicial. Configuraremos nuestro entorno SQL importaremos el archivo SQL que 
contiene los datos de mint classics en SQL workbench. 
Este es un paso preparatorio muy importante para poder comenzar nuestro proyecto o análisis de 
datos .

Creando el espacio de trabajo y configuración local
