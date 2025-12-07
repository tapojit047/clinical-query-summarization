# Clinical Query Summarization

This project is a system for summarizing medical articles to answer clinical questions. Given a health-related question and relevant medical articles, the models generate concise abstractive summaries. We fine-tune two transformer models: **Gemma-2** (decoder-only) and **Long-T5** (encoder-decoder) using parameter-efficient LoRA fine-tuning.

## Requirements

- Python 3.8+
- CUDA-compatible GPU (tested on Tesla P100 16GB)
- Jupyter Notebook or JupyterLab

## How to Run

### 1. Set Up the Environment

First, open a terminal and create a virtual environment:

```bash
python -m venv env
source env/bin/activate
```

### 2. Run Long-T5 Model

1. Open `long-t5/long_t5_lora_finetune.ipynb` in Jupyter
2. Run the first cell to install all dependencies (PyTorch, transformers, peft, etc.)
3. Restart the kernel after installation
4. Run all cells from top to bottom

The notebook will:
- Load the clinical QA dataset
- Run baseline inference with the pre-trained Long-T5 model
- Fine-tune the model using LoRA
- Generate predictions with the fine-tuned model
- Evaluate using ROUGE and BERTScore metrics
- Save all outputs to `long-t5/outputs/`

### 3. Run Gemma-2 Model

1. Open `gemma_2/gemma2_finetune.ipynb` in Jupyter
2. Run the first cell to install dependencies
3. Restart the kernel after installation
4. Run all cells from top to bottom

The notebook will:
- Load the clinical QA dataset
- Run baseline inference with Gemma-2
- Fine-tune using LoRA
- Evaluate and compare results
- Save outputs to `gemma_2/outputs/`

**Note:** Gemma-2 requires accepting the model license on Hugging Face. You may need to log in with `huggingface-cli login`.

## Output Files

After running the notebooks, you will find these files in each model's `outputs/` folder:

- `baseline_validation_predictions.json` - Pre-trained model predictions on validation set
- `baseline_test_predictions.json` - Pre-trained model predictions on test set
- `finetuned_validation_predictions.json` - Fine-tuned model predictions on validation set
- `finetuned_test_predictions.json` - Fine-tuned model predictions on test set
- `evaluation_metrics.json` - ROUGE and BERTScore results
- `lora_adapter/` - Saved LoRA weights

## Evaluation Metrics

The models are evaluated using:
- **ROUGE-1, ROUGE-2, ROUGE-L** - Measures n-gram overlap between generated and reference summaries
- **BERTScore** - Measures semantic similarity using BERT embeddings
