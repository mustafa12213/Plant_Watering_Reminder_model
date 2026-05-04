# Plant_Watering_Reminder_model
🏗️ Architecture: Plant Health Classifier
The model utilizes Transfer Learning with a specialized head to classify plant health into three categories: Healthy, Slightly Dry, and Very Dry.

Backbone: MobileNetV2 (Pre-trained on ImageNet).
Fine-Tuning Strategy: Top 40 layers unfrozen for domain-specific feature adaptation.
Custom Head:
Global Average Pooling 2D.
Dual Batch Normalization layers for training stability.
Progressive Dropout (0.5 → 0.4 → 0.3) to prevent overfitting.
L2 Regularization (0.001) on Dense layers (256 & 128 units).
Inference Optimization: Implements Test-Time Augmentation (TTA), averaging 10 augmented views per image to increase real-world reliability.
📊 Performance Metrics
Final evaluation conducted on a balanced test set of ~8,700 images.

Metric	Value
Overall Test Accuracy	94.01%
AUC-ROC (Average)	~0.99
Healthy (Recall)	99.86%
Very Dry (Recall)	99.26%
Slightly Dry (Recall)	80.81%
💡 Key Takeaways
Robustness: Near-perfect identification of healthy and severely dehydrated plants.
Efficiency: Uses MobileNetV2 for a lightweight footprint, suitable for future mobile deployment.
Reliability: Confidence scores and TTA ensure that the watering advice provided is based on averaged visual consensus rather than a single frame.

