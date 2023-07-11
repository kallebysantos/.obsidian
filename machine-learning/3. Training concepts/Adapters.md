Adapters are a **modular** and **lightweight** technique used in [[Fine-Tuning]] of
large pre-trained language models. They enable task-specific adaptation
without modifying the entire architecture of the pre-trained model.
Adapters consist of small, task-specific neural networks that are added 
to the pre-trained model.

**Key aspects of adapters**:
1. **Pre-Training**:
	Initially, a large-scale language model, such as [[Introducing LLaMA|LLaMA]], is 
	**pre-trained** on a vast corpus of unlabeled text data.
	
	During pre-training, the model **learns to understand** and generate
	text by **predicting** missing words or **next-word probabilities** based 
	on the surrounding context. This pre-training phase imparts general
	language understanding to the model.
	
2. **Adapter Architecture**:
	Adapters are small and task-specific neural networks that are added
	to the pre-trained model without modifying its original 
	architecture. These adapters are typically composed of few 
	additional layers that are specific to the largest task.
	 
3. **Adapter Parameters**:
	Each adapter has its own set of learnable [[parameters]]. During the
	[[fine-tuning]] process, theses [[parameters]] are adjusted to adapt the
	pre-trained model to a specific task. The rest of the pre-trained model remains frozen, preserving the original knowledge acquired 
	during pre-training.
	
4. **Adapter Initialization**:
	Initially, the parameters of the adapters are randomly initialized. Alternatively, they can be initialized with pre-trained task-specific weights from previous similar tasks, providing a good starting point for the fine-tuning process.
    
5. **Task-specific Data**:
	Task-specific labeled or annotated data is collected or generated to train the adapters. 
	
	This data is representative of the target task and includes examples with corresponding ground truth labels or annotations.
    
6. **Adapter Fine-tuning**:
	The pre-trained model, along with the task-specific adapters, is fine-tuned on the task-specific data. The adapters are trained while keeping the rest of the pre-trained model fixed. 
	
	This process helps the model specialize in the target task while preserving the knowledge learned during pre-training.
    
7. **Iterative Training**:
	Adapter fine-tuning is typically performed in an iterative manner. In each iteration, the adapters are updated using task-specific data, and the model's performance is evaluated on a separate validation or development set. 
	
	This evaluation guides the selection of the best adapter configuration and helps avoid overfitting.
    
8. **Adapter Sharing**:
	A notable advantage of adapter-tuning is the ability to share adapters across multiple tasks. Since adapters are lightweight and task-specific, they can be easily transferred or reused between related tasks, reducing the need for extensive model retraining.
    
9. **Deployment and Inference**:
	Once the adapter-tuning process is complete, the fine-tuned model with task-specific adapters can be deployed and used for making predictions or generating output on new, unseen data related to the specific task. 
	
	Inference involves passing the input through the appropriate adapters for the target task.