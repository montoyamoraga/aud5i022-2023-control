# aud5i022-2023-control

## pauta

- punto base
- asistencia

### materiales

- Arduino UNO[R3]
- Protoboard 60 filas
- 3 Buzzer
- 3 LEDs
- 3 Resistores (220 Ω)
- Potenciometro (10K Ω)
- 2 Switch
- Boton pulsador
- Muchos cables dupont (16)
- Cable USB

### circuito



### código

```ino

// arpegiador canon

//tiempo del ciclo en segundos
int tiempoCiclo = 800;

int tiempoFrec = 120;

// pines
int buzzer1 = 11;
int buzzer2 = 12;
int buzzer3 = 13;
int perilla = A0;

// frecuencia ahora
int frec = 440;
// freacuencias almacenadas
int frec2 = 0;
int frec3 = 0;

void setup() {

  pinMode(11, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(13, OUTPUT);

  Serial.begin(9600);

}

void loop() {

  // asignamos una frecuencia segun la perilla
  frec = analogRead(perilla) * 2;

  //reproducimos las frecuencias en secuencia
  tone(buzzer1, frec, tiempoFrec);//tone(pin, freq, time)
  delay(tiempoFrec);// esperamos a que termine de sonar
  tone(buzzer2, frec2, tiempoFrec);
  delay(tiempoFrec);
  tone(buzzer3, frec3, tiempoFrec);

  // imprimimos las frecuencia en el monitor serial
  Serial.println(frec);
  Serial.println(frec2);
  Serial.println(frec3);

  // asignamos frecuencias armonicas a frec
  frec3 = 2*frec2;
  frec2 = 2*frec/3;

  delay(tiempoFrec);


}
```


### imágenes



### conclusiones

![alt](img/foto.jpg "foto en clases")


inspiracion: proyecto de estudiante del semestre pasado

* https://github.com/jibbx/AV-ERDDEL

![alt](foto.jpg "foto en clases")
