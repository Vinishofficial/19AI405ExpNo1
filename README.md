<h1>ExpNo 1 : Developing AI Agent with PEAS Description</h1>
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>

<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>

<h3>Theory</h3>
<h3>Plant Watering Agent:</h3>
<p>This agent monitors the soil moisture level of plants and waters them if the moisture is below a threshold (considered dry). The environment consists of multiple plants in different locations. The agent senses the moisture level of each plant and decides whether to water it. The agent’s performance is measured by the number of plants properly watered, and each unnecessary movement reduces performance. Hence, the agent ensures plants are properly maintained.</p>

<hr>
<h3>PEAS DESCRIPTION:</h3>
<table border="1" cellpadding="5" cellspacing="0">
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
    <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
  <tr>
    <td><strong>Plant watering agent</strong></td>
    <td><strong>Watering dry plants, agent movement</strong></td>
    <td><strong>Plants, Soil Moisture</strong></td>
    <td><strong>Watering mechanism</strong></td>
    <td><strong>Location, Soil Moisture level</strong></td>
  </tr>
</table>

<hr>
<h3>DESIGN STEPS</h3>
<p><strong>STEP 1:</strong> Input: Soil moisture level of plants, Location of each plant.</p>
<p><strong>STEP 2:</strong> Output: Water the plant if the soil is dry.</p>
<p><strong>STEP 3:</strong> Develop PEAS description based on performance, environment, actuators, and sensors.</p>
<p><strong>STEP 4:</strong> Implement the AI agent: Check soil moisture of each plant and water if dry.</p>
<p><strong>STEP 5:</strong> Measure performance: Increment for watering, decrement for unnecessary movement.</p>

<hr>
<h3>CODE:</h3>

<textarea id="codeBlock" rows="35" cols="100" readonly>
import random

class PlantWateringAgent:
    def __init__(self):
        self.plants = ["Plant 1", "Plant 2", "Plant 3"]
        self.performance = 0

    def sense(self, moisture_level):
        """Sense the moisture level of a plant"""
        return moisture_level

    def act(self, plant, moisture_level):
        """Act based on moisture level"""
        if moisture_level < 30:  # Less than 30% moisture → water the plant
            self.water_plant(plant)
        else:
            self.skip_plant(plant)

    def water_plant(self, plant):
        print(f"{plant}: Soil is dry! Watering the plant.")
        self.performance += 1

    def skip_plant(self, plant):
        print(f"{plant}: Soil is moist. No watering needed.")

# Main function to test the agent
def main():
    agent = PlantWateringAgent()
    # Example moisture levels (can be replaced with real sensor input)
    plant_moisture = [25, 45, 20]  # % moisture for each plant

    for i, moisture in enumerate(plant_moisture):
        plant = agent.plants[i]
        sensed_moisture = agent.sense(moisture)
        agent.act(plant, sensed_moisture)

    print(f"Total actions performed by agent: {agent.performance}")

if __name__ == "__main__":
    main()
</textarea>
<br><br>
<button onclick="copyCode()">Copy Code</button>

<script>
function copyCode() {
  var copyText = document.getElementById("codeBlock");
  copyText.select();
  copyText.setSelectionRange(0, 99999); // For mobile devices
  document.execCommand("copy");
  alert("Code copied to clipboard!");
}
</script>

<hr>
<h3>OUTPUT:</h3>
<pre>
Plant 1: Soil is dry! Watering the plant.
Plant 2: Soil is moist. No watering needed.
Plant 3: Soil is dry! Watering the plant.

Total actions performed by agent: 2
</pre>
