# Object Detection with Federated Learning

The basic idea behind this project was prompted by the recent developments in the deployment of satellite constellations, computing on satellites, and the deployment of deep learning models on edge devices. Large-scale Low Earth Orbit (LEO) satellite deployments can collect massive amounts of Earth imagery and sensory data for the scenarios mentioned above. However, it is not truly feasible for the satellites to downlink all the high-resolution images to the ground stations, then let the models there train or infer on this data, and repeat this cycle for several iterations, for a real-time object detection case. Bandwidth issues, isolated connectivity, and breaches during the transmission of data between satellites and the ground station are some of the concerns. The idea is that there could be a way such that we can train a model on every satellite that will have its own dataset and this model then can be used later to detect objects in real-time. We can leverage Federated Learning(FL), wherein the satellites collaboratively train ML models locally and infer on the new data locally, without sharing the captured images with the ground station and then send these model parameters to the ground station for aggregation with all other local model parameters. Aggregation of the models at the server/ground station ensures that the global model is an improvised version that could be sent back to the satellites/clients for further local training.

To imitate this scenario in the form of a machine learning project, I chose the YOLOv3 model that would be trained on the PASCAL VOC dataset. I have chosen the Flower framework to implement the federated learning architecture. I have chosen the number of clients to be 2 and the averaging algorithm to be the FedAvg algorithm.

**TL;DR**: Train the Object Detection task at hand in a Distributed Machine Learning fashion.


https://github.com/user-attachments/assets/1325bbbc-8894-4cf5-9283-8dcbd44b5164



Credit: 
1. https://github.com/xuexingyu24/YOLO-V3-in-Pytorch-A-Tutorial-on-Implementation-of-YOLO-V3-Algorithm
2. https://flower.ai/
