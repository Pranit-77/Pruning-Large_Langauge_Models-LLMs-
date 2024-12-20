# Pruning-Large_Langauge_Models-LLMs-

# Pruning Mistral 7B and LLama 7B Models

The following commands were used to prune the Mistral 7B and LLama 7B models.

### Mistral 7B Pruning and Mistral 7B Pruning

```bash
python main2.py \
   --model "mistralai/Mistral-7B-Instruct-v0.1" \
   --prune_method wanda \
   --sparsity_ratio 0.75 \
   --sparsity_type unstructured \
   --save out/llama_7b/unstructured/wanda/ \
   --save_model /mnt/parscratch/users/lip23pdr/mistral_75_pruned


python main2.py \
   --model "meta-llama/Llama-2-7b-hf" \
   --prune_method wanda \
   --sparsity_ratio 0.25 \
   --sparsity_type unstructured \
   --save out/llama_7b/unstructured/wanda/ \
   --save_model /mnt/parscratch/users/lip23pdr/llama2_25_pruned
```
- The above commands were used to prune the Mistral 7B and LLama 7B models.
- Change the sparsity ratio accordingly to get the desired pruned models.
- The models were saved and then further used to evaluate the **CommonsenseQA** datasets and the **ARC Challenge** dataset.
- You can find the `.ipynb` files for every sparsity ratio, model, and dataset attached as well.
- Pruned models were not committed to this GitHub repository, as they take over 200GB of data storage, which GitHub does not allow.
- Use the above commands and tweak the parameters as necessary. Make sure to add the tokenizers while using the models from Hugging Face.


## Final Result

## For CommonsenseQA Dataset

| Model          | Sparsity | WikiText Perplexity | Accuracy | Precision | Recall  | F1-Score |
|----------------|----------|---------------------|----------|-----------|---------|----------|
| LLama 7B       | 0.25     | 5.75                | 49.22    | 49.51     | 49.22   | 49.27    |
| LLama 7B       | 0.33     | 6.01                | 48.16    | 48.37     | 48.16   | 48.20    |
| LLama 7B       | 0.50     | 7.09                | 33.50    | 33.52     | 33.50   | 33.46    |
| LLama 7B       | 0.66     | 40.27               | 16.71    | 16.74     | 16.71   | 16.70    |
| LLama 7B       | 0.75     | 2021.86             | 17.77    | 17.68     | 17.77   | 17.71    |
| Mistral 7B     | 0.25     | 5.97                | 60.93    | 61.09     | 60.93   | 60.93    |
| Mistral 7B     | 0.33     | 6.05                | 59.13    | 59.23     | 59.13   | 59.12    |
| Mistral 7B     | 0.50     | 6.69                | 57.41    | 57.55     | 57.41   | 57.36    |
| Mistral 7B     | 0.66     | 11.85               | 37.51    | 37.50     | 37.51   | 37.45    |
| Mistral 7B     | 0.75     | 50.42               | 20.97    | 20.96     | 20.97   | 20.94    |


## For ARC Dataset

| Model          | Sparsity | WikiText Perplexity | Accuracy | Precision | Recall  | F1-Score |
|----------------|----------|---------------------|----------|-----------|---------|----------|
| LLama 7B       | 0.25     | 5.75                | 22.41    | 25.51     | 18.26   | 22.47    |
| LLama 7B       | 0.33     | 6.01                | 22.07    | 24.62     | 17.74   | 19.51    |
| LLama 7B       | 0.50     | 7.09                | 23.08    | 23.41     | 22.47   | 19.52    |
| LLama 7B       | 0.66     | 40.27               | 23.08    | 23.75     | 21.81   | 21.33    |
| LLama 7B       | 0.75     | 2021.86             | 20.40    | 21.27     | 19.52   | 22.64    |
| Mistral 7B     | 0.25     | 5.97                | 20.40    | 20.69     | 18.79   | 21.81    |
| Mistral 7B     | 0.33     | 6.05                | 22.41    | 24.95     | 18.21   | 22.64    |
| Mistral 7B     | 0.50     | 6.69                | 21.74    | 23.77     | 21.33   | 22.64    |
| Mistral 7B     | 0.66     | 11.85               | 21.74    | 23.75     | 22.64   | 21.81    |
| Mistral 7B     | 0.75     | 50.42               | 22.41    | 24.25     | 22.64   | 23.75    |



