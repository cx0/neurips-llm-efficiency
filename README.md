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

### Dataset

[open-otter](https://huggingface.co/datasets/onuralp/open-otter)

### Training logs

- W&B logs for each submission
- Axolotl `.yml` config files 

### Future experiments

- LoRA vs QLoRA vs [VeRA](https://arxiv.org/abs/2310.11454) vs [full FT](https://github.com/hitz-zentroa/GoLLIE/)
- NEFTune (see [issue](https://github.com/neelsjain/NEFTune/issues/1))
- Data mixture (a la DoReMi)
- Curriculum learning
- Model fusion/merge
