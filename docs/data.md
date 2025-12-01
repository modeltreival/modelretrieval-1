# Dataset and Resources

We plan to release data under the **GPL license**. The data will be publicly available online (e.g., GitHub).

## Subtask A: Language Models

### Queries (Tasks)

- **Source:** Public document classification datasets available on Hugging Face.
- **Details:** We will ensure diversity in data size, number of classes, etc. Queries are separated into development and test sets.

### Candidate Models

- **Source:** Pre-trained BERT models publicly available on Hugging Face.
- **Diversity:** Models will differ by structure, parameter size, pre-trained data, etc.

### Ground Truth

- The performance score of each candidate model is determined by organizers by fine-tuning it on the training/validation splits and evaluating on the test split.

!!! warning "Constraint"
For Subtask A, participants are **not allowed** to fine-tune the candidate models themselves.

---

## Subtask B: Style Transfer Models

### Query Images

- **Details:** Desired style images will be used as queries. These are generated using an original content image and a style-transfer model.
- **Sets:** Queries are separated into development and test sets.

### Candidate Models

- **Source:** Style-transfer models publicly available (e.g., Civitai).
- **Details:** Models will vary in the styles they can generate.

### Ground Truth

- For every query, we will provide a ground truth model ranked list.
