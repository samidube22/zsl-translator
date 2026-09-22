# Interactive Zimbabwean Sign Language (ZSL) Translator

An interactive, local-first web application for real-time hand tracking and gesture data collection in Zimbabwean Sign Language (ZSL). Built as a B.Tech Capstone research project.

# Key Features
* Real-Time Hand Tracking: Extract 3D hand landmarks at ≥26 FPS using Google MediaPipe and HTML5 Canvas without GPU acceleration.
* Low Memory Footprint: Optimised front-end execution keeping client-side memory usage under 200MB.
* Dataset Capture Pipeline:** Interface for recording multi-signer gesture sessions and exporting structured coordinate data in JSON format.
* Multimodal Accessibility: Integrated Text-to-Speech (TTS) API for real-time auditory status updates.

## Tech Stack
* Frontend:React, TypeScript, Vite, Tailwind CSS
* Computer Vision: MediaPipe Hands API, WebGL
* State & Data Management: Local Storage, Structured JSON Export
