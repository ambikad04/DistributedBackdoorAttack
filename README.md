# **Federated Learning with Distributed Backdoor Attack**

This project demonstrates how Federated Learning (FL) behaves under a **Distributed Backdoor Attack** scenario, where multiple malicious clients collaboratively inject a hidden backdoor into the global model. It showcases the impact on the global model's accuracy and backdoor activation after training.

---

## **Features**

- **Federated Learning Workflow**: Simulates the full FL process, including data generation, local training, and global model aggregation.  
- **Collaborative Malicious Clients**: Implements a distributed backdoor attack where multiple clients inject targeted poisoned updates.  
- **Synthetic Data Generation**: Generates client-specific datasets for training, testing, and attack simulation.  
- **Backdoor Effect Analysis**: Evaluates both the global model’s performance on clean data and the activation of the backdoor on poisoned inputs.  

---

## **Installation**

### **Prerequisites**
- Python 3.8+  
- Required Libraries: PyTorch, NumPy  

### **Installation Steps**
1. Clone the repository:  
   ```bash
   git clone https://github.com/ambikad04/FL-DistributedBackdoorAttack.git  
   cd FL-DistributedBackdoorAttack  
   ```  

2. Install dependencies:  
   ```bash
   pip install torch numpy  
   ```  

---

## **Usage**

1. Run the script:  
   ```bash
   python FL-DistributedBackdoorAttack.py  
   ```  

2. Customize parameters:  
   - Modify the number of clients, global epochs, malicious client IDs, and backdoor triggers directly in the script for various scenarios.  

---

## **Code Structure**

### **Main Components**
1. **Data Generation (`create_client_data`)**:  
   Generates synthetic datasets for clients, including clean and backdoor-triggered inputs.  

2. **Model Definition (`SimpleModel`)**:  
   Defines a simple neural network for multi-class classification.  

3. **Local Training (`train_local_model`)**:  
   Each client trains their model locally on their dataset, including malicious training for compromised clients.  

4. **Backdoor Attack (`inject_backdoor`)**:  
   Implements the backdoor attack by embedding specific patterns in input data and modifying corresponding labels.  

5. **Federated Learning (`federated_learning_with_backdoor`)**:  
   Manages the FL process, including malicious client updates and global aggregation.  

6. **Federated Averaging (`federated_averaging`)**:  
   Aggregates model updates from all clients into the global model.  

7. **Backdoor Evaluation (`evaluate_backdoor`)**:  
   Measures the backdoor attack success rate and clean data accuracy.  

---

## **Example Output**

Running the script generates logs similar to the following:  
```  
Client 2 and Client 4 are malicious in epoch 1.  
Global epoch 1 completed.  
Backdoor success rate: 85.00%  
Clean accuracy: 92.00%  

Client 2 and Client 4 are malicious in epoch 2.  
Global epoch 2 completed.  
Backdoor success rate: 90.00%  
Clean accuracy: 88.50%  
```  

---

## **Results**

The results demonstrate how a distributed backdoor attack impacts the global model. Key observations include:  
- A high backdoor success rate even when the global model performs well on clean data.  
- Variations in attack effectiveness based on the number of malicious clients, their training intensity, and the complexity of the backdoor trigger.  

---

## **Contributing**

Contributions are welcome! Fork the repository, implement your changes, and submit a pull request.  

---

## **Acknowledgments**  

This project is inspired by research on Federated Learning and explores its vulnerabilities under distributed backdoor attacks.  

