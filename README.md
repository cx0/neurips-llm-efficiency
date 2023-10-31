# llm-efficiency-submission

### First stage evaluation

Each submission folder includes a Dockerfile and python files required for `helm` evaluation. For convenience, here is a compressed file containing all submissions together: [all_submissions.zip](./all_submissions.zip). Team name for both tracks is `ziggurat`.

- 4090 track
	- [Submission #1](./4090_track/4090_submission_1.zip)
	- [Submission #2](./4090_track/4090_submission_2.zip)
	- [Submission #3](./4090_track/4090_submission_3.zip)

- A100 track
	- [Submission #1](./A100_track/A100_submission_1.zip)
	- [Submission #2](./A100_track/A100_submission_1.zip)
	- [Submission #3](./A100_track/A100_submission_3.zip)

### Models

All the adapters and merged models are available on Hugging Face: [model collection](https://huggingface.co/collections/onuralp/neurips-2023-llm-efficiency-653a942242bfd8801c3336e7). Here is a summary of all the experiments.

| Base model | Axolotl config | Training log | QLoRA r/alpha | Target modules | 
|:----------:|:----------:|:--------------:|:------------:|:-------:|
| Llama-2-7b            |   [yml file](./axolotl_configs/Llama-2-7b-03.yml)             |     W&B logs      |    1 (16/16)        |    gate, up, down*          |
| Llama-2-13b           |   [yml file](./axolotl_configs/Llama-2-13b-01.yml)             |   W&B logs           |   1 (16/16)      |   gate, up, down           |
| Llama-2-13b           |    [yml file](./axolotl_configs/Llama-2-13b-02.yml)            |   W&B logs           |    1 (64/64)     |    gate,up, down          |
| Mistral-7b-v0.1           |  [yml file](./axolotl_configs/Mistral-01.yml)              |    W&B logs          |     2 (32/16)    |  all modules            |
| Mistral-7b-v0.1           | [yml file](./axolotl_configs/Mistral-02.yml)               |    W&B logs          |     2 (32/16)    |    gate, up, down          |
| Mistral-7b-v0.1           | [yml file](./axolotl_configs/Mistral-03.yml)               |    W&B logs          |     2 (64/32)    |  gate, up, down            |

\*  Targeting `gate_proj`, `down_proj`, and `up_proj` modules follows the finetuning recipes reported by [He et al. 2022](https://github.com/jxhe/unify-parameter-efficient-tuning) and [Lee and Hunter et al. 2023](https://github.com/arielnlee/Platypus).

### Dataset

Inspired by the performance of Open-Platypus dataset, we have curated a similar dataset while limiting each contributing subset to datasets with permissive licences. Please see HF for additional information on [Open-Otter dataset](https://huggingface.co/datasets/onuralp/open-otter).

### Future experiments

- LoRA vs QLoRA vs [VeRA](https://arxiv.org/abs/2310.11454) vs [full FT](https://github.com/hitz-zentroa/GoLLIE/)
- NEFTune (see [issue](https://github.com/neelsjain/NEFTune/issues/1))
- Data mixture (a la DoReMi)
- Curriculum learning (no compelling evidence that this works?)
- Model fusion/merge
