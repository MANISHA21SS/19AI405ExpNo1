## ExpNo 1 :Developing AI Agent with PEAS Description
## Name: Manisha selvakumari.S.S.
## Register Number: 212223220055

## AIM:
To find the PEAS description for the given AI problem and develop an AI agent.

## Theory:

Medicine prescribing agent:
Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.

## PEAS DESCRIPTION:
<img width="1046" height="129" alt="image" src="https://github.com/user-attachments/assets/e642b2a7-9d71-4ec0-a1b8-ec8603ec87b5" />

## ALGORITHM:

STEP 1:Identifying the input:
Temperature from patients, Location.

STEP 2:Identifying the output:
Prescribe medicine if the patient in a random has a fever.

STEP 3:Developing the PEAS description:
PEAS description is developed by the performance, environment, actuators, and sensors in an agent.

STEP 4:Implementing the AI agent:
Treat unhealthy patients in each room. And check for the unhealthy patients in random room

STEP 5:
Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented.

## PROGRAM:
import random
import time
class HealthMonitoringAgent:
    def __init__(self, patient_data, sensors, actuators):
        self.patient_data = patient_data
        self.sensors = sensors
        self.actuators = actuators
        print(f"Monitoring health for patient: {self.patient_data['name']}")
    def monitor_health(self):
        while True:
            current_health_state = self.sensors.get_health_state()
            action = self.choose_action(current_health_state)
            print("Current Health State:", current_health_state)
            self.actuators.perform_action(action)
            if action == "No specific action needed":
                print("Patient is stable. Monitoring stopped.")
                break
            time.sleep(1)
    def choose_action(self, current_health_state):
        if current_health_state['heart_rate'] > 120:
            return "Alert healthcare provider: High heart rate detected"
        elif current_health_state['blood_pressure'] > 140:
            return "Alert healthcare provider: High blood pressure detected"
        elif current_health_state['temperature'] > 38:
            return "Recommend rest and monitor temperature"
        else:
            return "No specific action needed"
class HealthSensors:
    def get_health_state(self):
        return {
            'heart_rate': random.randint(60, 150),
            'blood_pressure': random.randint(90, 160),
            'temperature': round(random.uniform(36.0, 38.5), 1)
        }
class HealthActuators:
    def perform_action(self, action):
        print("Action:", action)
if __name__ == "__main__":
    patient_data = {
        'patient_id': 123,
        'name': 'John Doe',
        'age': 35
    }
    sensors = HealthSensors()
    actuators = HealthActuators()
    agent = HealthMonitoringAgent(patient_data, sensors, actuators)
    agent.monitor_health()

 ## OUTPUT:
   <img width="802" height="91" alt="image" src="https://github.com/user-attachments/assets/b42ae778-e728-4f99-89df-12592ed33ef1" />

 ## RESULT:
 Hence, the solution for the given AI problem is found.

