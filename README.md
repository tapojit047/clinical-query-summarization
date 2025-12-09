# Clinical Query Summarization

This project develops a system for summarizing medical articles to answer clinical questions. Given a health-related question and relevant medical articles, the models generate concise abstractive summaries. More details about the task: [Task Deskcription](https://github.com/tapojit047/clinical-query-summarization/blob/main/task-description.md)

GitHub Link to the Project: [Github](https://github.com/tapojit047/clinical-query-summarization)

We fine-tune two transformer models: `google/gemma-2-2b` (decoder-only) and `google/long-t5-tglobal-base` (encoder-decoder) and `t5-small` (encoder-decoder). 

## Compute Environment

- **Long-T5**: Chameleon Cloud ( GPU_P100 baremetal Machine)
- **Gemma-2**: Google Colab
- **t5-small**: Google Colab

## Requirements

- Python 3.8+
- CUDA-compatible GPU (tested on Tesla P100 16GB)
- Jupyter Notebook or JupyterLab

## How to Run

### Long-T5 Model (Chameleon Cloud)

#### 1. Set Up the Environment

First, open a terminal and create a virtual environment:

```bash
python -m venv env
source env/bin/activate
```

#### 2. Run Long-T5 Model

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

### Gemma-2 Model (Google Colab)

Run the Gemma-2 notebook directly in Google Colab: [Open in Colab](https://colab.research.google.com/drive/1pU83U_tvx3HnAkyE71P-KbBh2aLpiv_f#scrollTo=fOMq-Yvqn3iB)

1. Mount your Google Drive with the dataset and update the `DATA_DIR` with your dataset directory.
2. Run each cell one by one from top to bottom

**Note:** Gemma-2 requires accepting the model license on Hugging Face. You may need to log in with `huggingface-cli login`.

### T5-Small Model (Google Colab)

Run the T5-Small notebook directly in Google Colab: [Open in Colab](https://colab.research.google.com/drive/1shu_HxMxDCIomuIb93qcTR6bhNASlANz?authuser=1#scrollTo=c3c71af7)

1. Mount your Google Drive with the dataset and change the `BASE_DIR`
2. Run each cell one by one from top to bottom

## Output Files

After running the notebooks, you will find these files in each model's `outputs/` folder.

