# Tech_Squad

Solution Architecture 
  The proposed AI-powered tutor is designed to deliver personalized, multimodal learning experiences for dyslexic students without relying on continuous internet access. The architecture is built on an offline-first Edge AI model using NVIDIA Jetson hardware to ensure accessibility in rural and underserved regions. The key components of his architecture include the Input Layer, Adaptive AI Engine, Multi-Modal Content Layer, Local Database, and Progress Dashboard. 

1. Hardware Layer 
  The system is deployed on NVIDIA Jetson Nano/Orin devices which offer GPU acceleration for real-time AI inference on the edge. These compact devices support offline model execution and interface seamlessly with audio input (microphone), handwriting input (touchscreen/stylus), and display output (HDMI or LCD). 
2. User Interaction Layer 
    The system starts with a registration/login module that allows students or parents to create and manage profiles. This data is stored locally in an SQLite database, including user details,preferred language, and session history. Upon login, the tutor loads the personalized profile and progress. 
3. Input Modules 
  Two major inputs drive adaptive learning: 
  • Speech Recognition: Open-source models like Whisper by OpenAI are integrated to transcribe spoken words. The engine also provides phonetic feedback, helping students   
    recognize pronunciation errors and practice correct articulation.
  • Handwriting Pattern Detection: Using OpenCV and ML models, the system analyzes handwriting inputs captured via stylus or touchscreen. It detects spelling errors,writing 
    speed, and stroke patterns, providing tailored feedback. 
4. Neuro-Adaptive AI Engine 
  This is the core intelligence module, responsible for adjusting lesson content dynamically. It processes input data from speech and handwriting, compares it against expected patterns, and determines: 
        • If the student is ready for the next level 
        • If the content should be simplified or reinforced 
        • Which sensory channels (text, audio, animation) are most effective 
   This decision logic is based on pre-trained ML models running locally and continuously updated using student performance data. 
5. Multi-Modal Content Delivery 
  Learning materials are delivered through an interactive, multi-sensory interface, combining: 
  • Visual aids (text, images, animations) 
  • Audio instructions (narration or phonetic feedback) 
  • Interactive tasks (drag-and-drop spelling, writing practice) 
  These lessons are optimized for dyslexic learners with large fonts, minimal distractions, and guided navigation. 
6. Local Database and Storage 
  A lightweight SQLite database stores all user data, activity logs, performance metrics, and session histories. This enables persistent local tracking without requiring      cloud storage or internet. 
7. Progress Monitoring Dashboard 
  A simple dashboard is available for teachers or parents, visualizing: 
    • Skill improvement trends 
    • Module-wise performance 
    • Areas needing attention 
   This dashboard is also rendered offline using local data. 
8. Optional Cloud Sync 
   Though primarily offline, the system can optionally sync progress via USB or over the internet when available, for data backup or curriculum updates.
