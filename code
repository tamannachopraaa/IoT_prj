#include <DHT.h>

#define DHTPIN 2          // Pin connected to the DATA pin of the DHT11
#define DHTTYPE DHT11     // Define the type of DHT sensor
#define MQ2PIN A0        // Pin connected to the MQ-2 analog output

DHT dht(DHTPIN, DHTTYPE); // Initialize DHT sensor

void setup() {
  Serial.begin(9600);     // Start serial communication at 9600 bps
  dht.begin();            // Initialize the DHT11 sensor
}

void loop() {
  // Wait a few seconds between measurements
  delay(2000);

  // Read temperature and humidity from DHT11
  float temperature = dht.readTemperature();
  float humidity = dht.readHumidity();

  // Read the MQ-2 sensor value
  int mq2Value = analogRead(MQ2PIN);

  // Check if any DHT reads failed and exit early
  if (isnan(temperature) || isnan(humidity)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  // Print temperature and humidity to the Serial Monitor
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.println(" %");

  // Print MQ-2 sensor value
  Serial.print("MQ-2 Sensor Value: ");
  Serial.println(mq2Value);
}
