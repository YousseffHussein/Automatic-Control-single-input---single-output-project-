#include <Wire.h>

// Pin definitions
const int motorPin1 = 2;   // Motor driver input 1
const int motorPin2 = 3;   // Motor driver input 2
const int enablePin = 9;   // Motor driver enable (PWM)
const int pot1Pin = A0;    // Manual potentiometer
const int pot2Pin = A1;    // Motor-driven potentiometer

// Variables
int pot1Value = 0;
int pot2Value = 0;
const int tolerance = 12;

void setup() {
  pinMode(motorPin1, OUTPUT);
  pinMode(motorPin2, OUTPUT);
  pinMode(enablePin, OUTPUT);

  // Ensure motor is stopped initially
  stopMotor();

  Serial.begin(9600); // Debugging
}

void loop() {
  // Read both potentiometers
  pot1Value = analogRead(pot1Pin);
  pot2Value = analogRead(pot2Pin);

  // Print values for debugging
  Serial.print("Manual: ");
  Serial.print(pot1Value);
  Serial.print(" | Motor: ");
  Serial.println(pot2Value);

  // Calculate the difference
  int difference = pot1Value - pot2Value;

  // If difference is within tolerance, stop the motor
  if (abs(difference) <= tolerance) {
    stopMotor();
  } 
  else {
    // Optional: dynamically scale speed based on how far off we are
    int speed = map(abs(difference), 0, 1023, 100, 255); // Adjust min/max as needed

    if (difference > 0) {
      rotateClockwise(speed);  // pot1 is higher
    } else {
      rotateCounterClockwise(speed); // pot1 is lower
    }
  }

  delay(30); // Small delay for stability
}

// Helper motor functions
void rotateClockwise(int speed) {
  digitalWrite(motorPin1, HIGH);
  digitalWrite(motorPin2, LOW);
  analogWrite(enablePin, speed);
}

void rotateCounterClockwise(int speed) {
  digitalWrite(motorPin1, LOW);
  digitalWrite(motorPin2, HIGH);
  analogWrite(enablePin, speed);
}

void stopMotor() {
  digitalWrite(motorPin1, LOW);
  digitalWrite(motorPin2, LOW);
  analogWrite(enablePin, 0);
}
