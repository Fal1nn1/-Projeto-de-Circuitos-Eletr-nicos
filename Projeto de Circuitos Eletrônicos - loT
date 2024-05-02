// Definindo os pinos
#define TEMP_SENSOR_PIN A0
#define MOTOR_PIN 3
#define LED_PIN 4
#define BUZZER_PIN 5

void setup() {
  // Definindo a referência de tensão como 5.0 volts
  analogReference(DEFAULT);

  // Inicializando os pinos
  pinMode(TEMP_SENSOR_PIN, INPUT);
  pinMode(MOTOR_PIN, OUTPUT);
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUZZER_PIN, OUTPUT);
  
  // Inicializando a comunicação serial
  Serial.begin(9600);
}

void loop() {
  // Lendo a temperatura
  int sensorValue = analogRead(TEMP_SENSOR_PIN);
  float voltage = sensorValue * (5.0 / 1023.0);
  float temperature = (voltage - 0.5) * 100 ;  // Convertendo para temperatura
  
  // Imprimindo a temperatura
  Serial.print("Temperatura: ");
  Serial.println(temperature);
  
  // Verificando a temperatura
  if (temperature >= 30 && temperature < 50) {
    digitalWrite(MOTOR_PIN, HIGH);  // Ligando o motor
    digitalWrite(LED_PIN, LOW);     // Desligando o LED
    digitalWrite(BUZZER_PIN, LOW);  // Desligando a buzina
  } else if (temperature >= 50) {
    digitalWrite(MOTOR_PIN, LOW);   // Desligando o motor
    digitalWrite(LED_PIN, HIGH);    // Ligando o LED
    digitalWrite(BUZZER_PIN, HIGH); // Ligando a buzina
  } else {
    digitalWrite(MOTOR_PIN, LOW);   // Desligando o motor
    digitalWrite(LED_PIN, LOW);     // Desligando o LED
    digitalWrite(BUZZER_PIN, LOW);  // Desligando a buzina
  }
  
  delay(1000);  // Aguardando 1 segundo antes da próxima leitura
}
