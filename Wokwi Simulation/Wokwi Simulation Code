// ===== Edge-AI Sepsis Prediction (Wokwi Compatible) =====

// Alert Pins
#define LED_HIGH 2
#define LED_MOD 16
#define BUZZER 4

void setup() {
  Serial.begin(115200);

  pinMode(LED_HIGH, OUTPUT);
  pinMode(LED_MOD, OUTPUT);
  pinMode(BUZZER, OUTPUT);

  Serial.println("=== Edge-AI Sepsis Prediction System ===");
}

void loop() {

  // -------- SENSOR SIMULATION (ADC) --------
  int temp_raw = analogRead(33);
  int hr_raw   = analogRead(34);
  int spo2_raw = analogRead(35);
  int rr_raw   = analogRead(32);

  float temperature = map(temp_raw, 0, 4095, 35, 41);   // °C
  float heartRate   = map(hr_raw,   0, 4095, 50, 140);  // bpm
  float spo2        = map(spo2_raw, 0, 4095, 85, 100);  // %
  float respRate    = map(rr_raw,   0, 4095, 10, 35);   // bpm

  // -------- FEATURE EXTRACTION --------
  float shockIndex = heartRate / 120.0;
  int riskScore = 0;

  if (temperature > 38.0) riskScore++;
  if (heartRate > 100) riskScore++;
  if (spo2 < 92) riskScore++;
  if (respRate > 22) riskScore++;
  if (shockIndex > 0.9) riskScore++;

  // -------- EDGE-AI INFERENCE --------
  String risk;
  if (riskScore >= 4) risk = "HIGH";
  else if (riskScore >= 2) risk = "MODERATE";
  else risk = "LOW";

  // -------- ALERT SYSTEM --------
  digitalWrite(LED_HIGH, LOW);
  digitalWrite(LED_MOD, LOW);
  digitalWrite(BUZZER, LOW);

  if (risk == "HIGH") {
    digitalWrite(LED_HIGH, HIGH);
    digitalWrite(BUZZER, HIGH);
  }
  else if (risk == "MODERATE") {
    digitalWrite(LED_MOD, HIGH);
  }

  // -------- MQTT PAYLOAD (SIMULATED) --------
  Serial.println("\n--- MQTT Publish (Encrypted Payload) ---");
  Serial.println("{");
  Serial.println("  \"patient_id\": \"ICU_01\",");
  Serial.println("  \"temperature\": " + String(temperature));
  Serial.println("  \"heart_rate\": " + String(heartRate));
  Serial.println("  \"spo2\": " + String(spo2));
  Serial.println("  \"resp_rate\": " + String(respRate));
  Serial.println("  \"risk\": \"" + risk + "\"");
  Serial.println("}");
  Serial.println("---------------------------------------");

  delay(2000);
}
