

# **Electrónica para Principiantes**

(Orientada a microcontroladroes Arduino...)
---

## **MÓDULO 1 - Adquisición de Herramientas Imprescindibles**  


---  


<table>
  <tr>
    <th>Herramienta</th>
    <th>Descripción</th>
    <th>Imágenes</th>
  </tr>
  <tr>
    <td><strong>1. Multímetro</strong></td>
    <td>Modelo básico económico y versátil para mediciones eléctricas.</td>
    <td><img src="img/multi.jpg" alt="Multímetro" width="200"></td>
  </tr>
  <tr>
    <td><strong>2. Placa Protoboard</strong></td>
    <td>Ideal para prototipado sin soldadura. Usar con cables jumper.</td>
    <td><img src="img/protoboard.jpg" alt="Protoboard" width="200"></td>
  </tr>
  <tr>
    <td><strong>3. Pinzas</strong></td>
    <td>Para manipulación precisa de componentes pequeños.</td>
    <td><img src="img/pinzas.jpg" alt="Pinzas" width="200"></td>
  </tr>
  <tr>
    <td><strong>4. Alicates</strong></td>
    <td>De corte  y sujeción. ¡No cortar materiales duros perderán su filo!</td>
    <td>
      <img src="img/alicates.jpg" width="200"><br>
      <img src="img/alicates.avif" width="200">
    </td>
  </tr>
  <tr>
    <td><strong>5. Soldador/Desoldador</strong></td>
    <td>Para soldadura sin plomo (RoHS). Temperatura ideal: 350-400°C.</td>
    <td>
      <img src="img/soldador.jpg" width="200">
      <img src="img/desoldador.jpg" width="200">
    </td>
  </tr>
  <tr>
    <td><strong>6. Fuente de Alimentación</strong></td>
    <td>Opción económica/casera (fuente PC) / profesional (variable).</td>
    <td>
      <img src="img/fuente.webp" width="200">
      <img src="img/fa.avif" width="200">
    </td>
  </tr>
  <tr>
    <td><strong>7. Destornilladores</strong></td>
    <td>De precisión para electrónica y estándar para mayor fuerza.</td>
    <td><img src="img/destornillador.jpg" width="200"></td>
  </tr>
</table>


---




# **Módulo 2: Conceptos Básicos de Electrónica**  
*(Fundamentos esenciales antes de programar microcontroladores)*  

---

## **1.1 Voltaje, Corriente y Resistencia**  

### **⚡ Ley de Ohm ver video**  

[![Ley de Ohm](https://img.youtube.com/vi/wHQrMuJAjak/0.jpg)](https://www.youtube.com/watch?v=wHQrMuJAjak)

 

### **📏 Uso del Multímetro ver Video:**  

[![Multimetro](https://img.youtube.com/vi/9XGib6fpRpw/maxresdefault.jpg)](https://www.youtube.com/watch?v=9XGib6fpRpw)


**⚠️ Precaución**: Nunca midas corriente en paralelo (podrías quemar el multímetro) y asegurate el rango de trabajo también (A  mA  uA).  

---

## **1.2 Componentes Básicos**  

### **🎨 Resistencias y Código de Colores**  
- **Cálculo rápido**:  
  <img src="img/codigos-colores-resistencias.webp" alt="Código de colores" width="500">  
 
[![Codigos colores de resistencias](https://img.youtube.com/vi/scl3N_HEpZQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=scl3N_HEpZQ)


### **💡 Diodos LEDs y Resistencias Limitadoras**  
- **Polaridad del LED**:  
  - **Ánodo (+)**: Pata más larga.  
  - **Cátodo (-)**: Lado plano del LED.  
- **Fórmula para calcular la resistencia del LED**:  
  ```  
  R = (V_fuente - V_LED) / I_LED  
  ```  
  - *Ejemplo*: Batería 5V, LED rojo (2V, 20mA):  
    ```  
    R = (5V - 2V) / 0.02A = 150 Ω  
    ```  

### **🔘 Pulsadores e Interruptores**  
- **Tipos**:  
  - **NA (Normalmente Abierto)**: Sólo cierra circuito al presionar.  
  - **Pull-up/Pull-down**: Evitan estados "flotantes" en microcontroladores.  
    ```cpp  
    // Ejemplo en Arduino (pull-up interno):  
    pinMode(boton, INPUT_PULLUP);  
    ```  

### **🛠️ Protoboard: Conexiones Básicas**  

#### **🔹 Estructura Básica**  
- **Agujeros estándar**: Espaciados a **2.54 mm** (para componentes como ICs, resistencias, LEDs).  
- **Filas centrales**:  
  - **5 agujeros por fila** conectados **horizontalmente** (pero **no entre columnas**).  
  - Ideal para insertar **circuitos integrados (ICs)** en la ranura central.  
- **Barras laterales (rojo/azul)**:  
  - Usadas para **alimentación (+Vcc)** y **tierra (GND)**.  
  - Conexión **vertical** (normalmente 25 agujeros por barra, a veces divididas en mitades).  

## Video Tutorial de Protoboard

Aprende a usar una protoboard con este video:

[![Cómo usar una Protoboard](https://img.youtube.com/vi/61C953UsX9I/0.jpg)](https://www.youtube.com/watch?v=61C953UsX9I)


#### **⚠️ Las protoboards no sirven para circuitos de alta frecuencia o corrientes altas (>1A). ¡Son solo para prototipado rápido!**
---

## **🔹 Práctica: Circuito LED + Resistencia + Batería**  

  <img src="img/circuito-con-led.webp" alt="Circuito_LED.png" width="500">  


### **Materiales**:  
- 1 LED rojo (2V).  
- 1 Resistencia de 220Ω.  
- Batería de 5V.  
- Protoboard y cables.  

### **Pasos**:  
1. Conecta el **ánodo del LED** (pata larga) a la **resistencia**.  
2. Une la resistencia al **positivo (+) de la batería**.  
3. Conecta el **cátodo del LED** (pata corta) al **negativo (-)**.  
4. ¡El LED debe encenderse!  

**💡 Reto opcional**:  
- Mide el voltaje en el LED con el multímetro (debe ser ≈2V).  
- Cambia la resistencia a 470Ω y observa cambios en el brillo.  

---

