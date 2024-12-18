## 👗 Fashion-MNIST 

👒 Here is the context for you: We have Fashion-MNIST dataset - Zalando's article images—consisting of a training set of 60,000 examples and a test set of 10,000 examples.

Our code trains a neural network on the dataset to classify clothing images into 10 categories (such as trouser, shirt, bag..). By using Distributed Training, we split the workload across multiple CPU workers to speed up training and handle this large dataset.

## 🏃‍➡️ How to run?

1) Log in to OpenShift AI and go to a Data Science Project. 

2) Run the first Notebook [0_basic_ray.ipynb](./0_basic_ray.ipynb) to verify that you are able to create a RayCluster.

3) Run the second Notebook [1_cluster_job_client.ipynb](./1_cluster_job_client.ipynb) to train the model by leveraging distributed training capability. It might take some time for the submitted job to switch from Pending state to Running state. 

You need to get similar logs as below and see `Training started without custom configuration.` which means the training job successfully started 🎉🙌

```
2024-08-21 20:46:47,637	INFO job_manager.py:530 -- Runtime env is setting up.
2024-08-21 20:48:57,075	INFO worker.py:1429 -- Using address 10.131.24.33:6379 set in the environment variable RAY_ADDRESS
2024-08-21 20:48:57,076	INFO worker.py:1564 -- Connecting to existing Ray cluster at address: 10.131.24.33:6379...
2024-08-21 20:48:57,090	INFO worker.py:1740 -- Connected to Ray cluster. View the dashboard at 10.131.24.33:8265 
2024-08-21 20:48:57,191	INFO tune.py:253 -- Initializing Ray automatically. For cluster usage or custom Ray initialization, call `ray.init(...)` before `<FrameworkTrainer>(...)`.

View detailed results here: /opt/app-root/src/ray_results/TorchTrainer_2024-08-21_20-48-57
To visualize your results with TensorBoard, run: `tensorboard --logdir /tmp/ray/session_2024-08-21_20-45-48_353360_1/artifacts/2024-08-21_20-48-57/TorchTrainer_2024-08-21_20-48-57/driver_artifacts`

Training started without custom configuration.
```

You can use OpenShift AI's Distributed Workload Metrics UI to see what is happening in your project.

Alternatively, you can check Ray Dashboard to see the status as well.

4) The job should take about 10-15 minutes. When you are done with it, can you please make sure to save some resources. Thank you! 🙏