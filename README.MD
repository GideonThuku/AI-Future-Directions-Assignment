# Part 1: Theoretical Analysis

## 1. Essay Questions

### Q1: Explain how Edge AI reduces latency and enhances privacy compared to cloud-based AI. Provide a real-world example (e.g., autonomous drones).

Edge AI refers to the practice of running artificial intelligence
algorithms directly on a local device rather than in a remote data
center. This offers major advantages:

**Latency Reduction** - Cloud AI requires sending data to a server and
waiting for results. - Edge AI processes data locally, eliminating
round-trip delays.

**Privacy Enhancement** - Cloud AI transmits sensitive data
externally. - Edge AI keeps data on-device, sending only high-level
alerts.

**Real-World Example: Autonomous Drones** - Cloud-based drone navigation
would suffer dangerous delays. - Edge-powered drones detect obstacles
instantly using onboard processors.

------------------------------------------------------------------------

### Q2: Compare Quantum AI and classical AI in solving optimization problems. What industries could benefit most from Quantum AI?

Quantum AI uses qubits that leverage **superposition** and
**entanglement**, enabling massive parallel exploration of solutions.
Classical AI uses bits and evaluates solutions sequentially.

**Industries benefiting from Quantum AI** - Pharmaceuticals (drug
discovery) - Finance (portfolio optimization) - Logistics (routing
optimization) - Materials science (simulation of new materials)

------------------------------------------------------------------------

# Part 2: Practical Implementation

## Task 1: Edge AI Prototype

**Tools:** TensorFlow Lite, Raspberry Pi / Google Colab

### Goal:

-   Train a lightweight image classifier for recyclable item detection.
-   Convert the model to TensorFlow Lite.
-   Test on a sample dataset.
-   Explain Edge AI benefits for real-time use.

### Deliverable:

-   Code
-   Report with accuracy metrics and deployment steps

### Project Summary (From PDF)

**Model:** MobileNetV2 (transfer learning)\
**Dataset:** TrashNet --- 2,527 images\
**Training:** 10 epochs in Google Colab\
**Conversion:** TFLite with dynamic range quantization\
**Performance:**\
- 14 MB → 3.5 MB\
- 91.5% → 90.8% accuracy\
- 160 ms → 35 ms inference time

**Edge AI Benefits** - Low latency\
- Privacy protection\
- No network dependency\
- Offline reliability

------------------------------------------------------------------------

## Task 2: AI-Driven IoT Concept

### Scenario:

Design a smart agriculture system using AI + IoT to predict crop yields.

### Requirements:

-   Sensors needed for prediction\
-   Proposed AI model\
-   Data flow diagram

### Sensors Needed

-   Soil moisture\
-   Soil temperature\
-   N-P-K nutrients\
-   Soil pH\
-   Ambient temperature & humidity\
-   Light (PAR) sensors

### Proposed AI Model

**Random Forest Regressor** - High accuracy\
- Handles missing data\
- Ideal for tabular sensor datasets\
- Provides feature importance

------------------------------------------------------------------------

## Data Flow Diagram (AI Processing Sensor Data)

    [FIELD SENSORS]
    (soil moisture, temperature, pH, NPK, humidity, PAR)
            |
            |  data collected every 30 minutes
            v
    [IoT GATEWAY]
     - aggregates sensor data
     - performs light preprocessing
            |
            |  sends via Wi-Fi / Cellular / LoRaWAN
            v
    [CLOUD PLATFORM]
     |-----------------------------|
     |  Time-Series Database       |
     |  (stores raw sensor data)   |
     |-----------------------------|
     |  AI Model Endpoint          |
     |  (Random Forest Regressor)  |
     |-----------------------------|
            |
            | scheduled job: "run prediction"
            v
    [AI PROCESSING]
     - cleans latest data
     - runs prediction
     - generates yield estimate
            |
            v
    [FARMER DASHBOARD]
     - real-time charts
     - AI yield predictions
     - alerts (e.g., "Low Nitrogen in Field 4")

------------------------------------------------------------------------
