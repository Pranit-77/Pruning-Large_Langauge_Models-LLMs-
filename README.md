# Pruning-Large_Langauge_Models-LLMs-

# Pruning Mistral 7B and LLama 7B Models

The following commands were used to prune the Mistral 7B and LLama 7B models.

### Mistral 7B Pruning

```bash
python main2.py \
   --model mistralai/Mistral-7B-Instruct-v0.1 \
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

- The above commands were used to prune the Mistral 7B and LLama 7B models.
- Change the sparsity ratio accordingly to get the desired pruned models.
- The models were saved and then further used to evaluate on **CommonsenseQA** datasets and the **ARC Challenge** dataset.
- You can find the `.ipynb` files for every sparsity ratio, model, and dataset attached as well.
- Pruned models were not committed to this GitHub repository, as they take more than 200GB of data storage, which GitHub does not allow.
- Use the above commands and tweak the parameters as necessary. Make sure to add the tokenizers while using the models from Hugging Face.
