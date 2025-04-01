

# **Electrónica para Principiantes**

(Orientada a microcontroladroes Arduino...)
---

## **MÓDULO 1 - Adquisición de Herramientas Imprescindibles**  

- **Multímetro**  
- **Placa Protoboard**  
- **Pinzas**  
- **Alicates de corte**  
- **Soldador y estaño**  
- **Desoldador de mano**  
- **Fuente de alimentación**  
- **Destornilladores de precisión (relojero)**  

---  

### **1. Multímetro**  
Un modelo básico es suficiente para empezar, ya que son económicos y versátiles.  

<img src="img/multi.jpg" alt="Multímetro" width="300">  

---  

### **2. Placa Protoboard**  
Ideal para probar circuitos sin soldar. Recomendable comprarla con cables de conexión (jumper wires).  

<img src="img/protoboard.jpg" alt="Protoboard" width="300">  

---  

### **3. Pinzas**  
Útiles para manipular componentes pequeños con precisión.  

<img src="img/pinzas.jpg" alt="Pinzas" width="300">  

---  

### **4. Alicates de Corte y de Sujección**  
Especializados para cortar pines de componentes. **No los uses para materiales duros** o perderán su filo.

<img src="img/alicates.jpg" alt="Alicates" width="300">  

Pequeños alicates de sujeccíon o agarre.

<img src="img/alicates.avif" alt="Alicates" width="300">  



---  

### **5. Soldador, Estaño y Desoldador**  
**Soldador sin plomo (RoHS)**.  

#### 🔥 **Aleaciones comunes y puntos de fusión**:  
- **Sn-Cu (99.3/0.7)**: 227°C  
- **SAC305 (Sn-Ag-Cu)**: 217–221°C  
- **SAC387 (Sn-Ag-Cu)**: 217–225°C  

⚠️ **Consejo**: Usa *flux* para mejorar la soldadura.  

<img src="img/soldador.jpg" alt="Soldador" width="300">  
<img src="img/desoldador.jpg" alt="Desoldador" width="300">  

---  

### **6. Fuente de Alimentación**  
**Opción económica**: Recicla una fuente de PC (cables útiles: **rojo (+5V)**, **amarillo (+12V)**, **negro (GND)**).  

<img src="img/fuente.webp" alt="Fuente de PC" width="300">  

**Opción profesional**: Fuente variable (ej: 0–30V, 0–5A/10A).  

<img src="img/fa.avif" alt="Fuente" width="300">  

---  

### **7. Destornilladores de Precisión**  
Para tornillos pequeños. Si necesitas más fuerza, añade un juego de destornilladores estándar.  

<img src="img/destornillador.jpg" alt="Destornilladores" width="300">  

---  

# **Módulo 2: Conceptos Básicos de Electrónica**  
*(Fundamentos esenciales antes de programar microcontroladores)*  

---

## **1.1 Voltaje, Corriente y Resistencia**  

### **🔌 Conceptos Clave**  
- **Voltaje (V)**: (unidad: Voltios).  
  - Ejemplo: Una batería de 9V tiene una diferencia de potencial de 9 voltios entre sus polos.  
- **Corriente (I)**: Flujo de electrones (unidad: Amperios).  
  - **¡Cuidado!**: Corrientes altas (>100mA) pueden dañar componentes.  
- **Resistencia (R)**: Oposición al flujo de corriente (unidad: Ohmios Ω).  

### **⚡ Ley de Ohm**  
Fórmula fundamental:  
```  
V = I × R  
```  
- **Ejemplo práctico**: Si un LED necesita 20mA (0.02A) y usamos una batería de 5V:  
  ```  
  R = V / I = 5V / 0.02A = 250 Ω  
  ```  
  *(Usaríamos una resistencia estándar de 220Ω o 330Ω).*  

### **📏 Uso del Multímetro**  
| **Funciòn** | **Què mide** | **Còmo usarlo** |  
|-------------|--------------|----------------|  
| **Voltaje (DC/AC)** | Diferencia de potencial entre dos puntos | Colocar puntas en paralelo al componente |  
| **Corriente (A)** | Flujo de electrones | Interrumpir el circuito y conectar en serie |  
| **Resistencia (Ω)** | Valor de resistencias | Medir con componente desconectado |  
| **Continuidad** | Cortocircuitos o conexiones rotas | Pitará si hay conexión (resistencia ≈ 0Ω) |  

**⚠️ Precaución**: Nunca midas corriente en paralelo (podrías quemar el multímetro).  

---

## **1.2 Componentes Básicos**  

### **🎨 Resistencias y Código de Colores**  
- **Cálculo rápido**:  
  <img src="img/codigo-colores.jpg" alt="Código de colores" width="400">  
  - Ejemplo: **Amarillo (4) - Violeta (7) - Rojo (×100) = 4700 Ω (4.7kΩ)**.  

- **Usos comunes**:  
  - Limitar corriente a LEDs.  
  - Dividir voltaje (divisor de tensión).  

### **💡 LEDs y Resistencias Limitadoras**  
- **Polaridad**:  
  - **Ánodo (+)**: Pata más larga.  
  - **Cátodo (-)**: Lado plano del LED.  
- **Fórmula para calcular la resistencia**:  
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
- **Estructura**:  
  <img src="img/protoboard-internal.jpg" alt="Conexiones protoboard" width="400">  
  - **Filas horizontales** (centrales): Conectadas en grupos de 5.  
  - **Barras laterales**: Para alimentación (+ y -).  

- **Regla de oro**:  
  > "Sigue las líneas azules/rojas para evitar cortocircuitos".  

---

## **🔹 Práctica: Circuito LED + Resistencia + Batería**  

### **Materiales**:  
- 1 LED rojo (2V).  
- 1 Resistencia de 220Ω.  
- Batería de 5V (o 2 pilas AA).  
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

## **📌 Resumen del Módulo 1**  
- **Ley de Ohm**: Relaciona voltaje, corriente y resistencia.  
- **Multímetro**: Herramienta clave para medir y diagnosticar.  
- **Componentes pasivos**: Resistencias, LEDs, pulsadores.  
- **Protoboard**: Base para prototipado rápido.  

**⬆️ Siguiente módulo**: Entradas/Salidas digitales con microcontroladores.  

--- 

**¿Dudas?** Revisa estos simuladores para practicar sin riesgos:  
- [Tinkercad Circuits](https://www.tinkercad.com/circuits)  
- [Falstad Circuit Simulator](https://falstad.com/circuit/)  

¿Quieres profundizar en algún tema en particular? 😊
