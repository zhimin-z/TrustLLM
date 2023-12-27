# **TustLLM: Trustworthiness in Large Language Models**

<img src="../images/logo.png" width="100%">

## **About**



## **Getting Start**

### **Installation**

Installation can be done using pypi:

```shell
pip install trustllm
```

### **Before Evaluation**

Download TrustLLM dataset:

```python
from trustllm import dataset_download

download_huggingface_dataset(save_path='save_path')
```



!!! note

    Please note that the LLM you use for evaluation should have a certain level of utility. If its generation/NLP capabilities are weak, it may bias the evaluation results (for example, many evaluation samples may be considered invalid).





The datasets are uniformly structured in JSON format, where each JSON file consists of a collection of dictionaries. Within each dictionary, there is a consistent key named `prompt`. Your task is to utilize the value of `prompt` key as the input for processing. After processing, you should store the result under a newly created key named `res` within the same dictionary. Here is an example to generate answer from your LLM:

```python
import json

filename = 'dataset_path.json'

# Load the data from the file
with open(filename, 'r') as file:
    data = json.load(file)

# Process each dictionary and add the 'res' key with the generated output
for element in data:
    element['res'] = generation(element['prompt'])  # Replace 'generation' with your function

# Write the modified data back to the file
with open(filename, 'w') as file:
    json.dump(data, file, indent=4)
```


## **Leaderboard**

If you want to view the performance of all models or upload the performance of your LLM, please refer to [this link](https://trustllmbenchmark.github.io/TrustLLM-Website/leaderboard.html).


## **Citation**
```shell

```

