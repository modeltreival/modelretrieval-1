# Task Definition

Our benchmark comprises two subtasks: **Language Model Retrieval** and **Image Style Transfer Model Retrieval**.

=== "Subtask A: Language Model"

    ![Tasl A](assets/images/task_a.png)

    ## Subtask A: Language Model Retrieval

    Participants are challenged to **predict each model's fine-tuned accuracy for document classification without performing any fine-tuning**.

    ### Background
    Selecting the most appropriate pre-trained model for a downstream task is challenging. Traditionally, this requires fine-tuning multiple candidates, which is computationally expensive. We aim to predict this ranking efficiently.

    ### Problem Definition
    Let $D^{train}=\{(x_{i}^{train},y_{i}^{train})\}_{i=1}^{M}$, $D^{val}=\{(x_{i}^{val},y_{i}^{val})\}_{i=1}^{N}$, and $D^{test}=\{(x_{i}^{test},y_{i}^{test})\}_{i=1}^{O}$ be the training, validation, and test splits of a document classification task.

    Given a set of $k$ pre-trained models $\{m_{1},...,m_{k}\}$, the goal is to rank the models in descending order of their performance on $D^{test}$ after fine-tuning.

    ### Participant Requirements
    * Participants must predict model ranking using only $D^{train}$, $D^{val}$, and unlabeled $x^{test}$.
    * **Usage of test labels is strictly prohibited**.
    * **No fine-tuning** on candidate models is permitted.

    ### Evaluation
    Each submitted ranking is compared against the ideal ranking using **nDCG@k**.

=== "Subtask B: Style Transfer"

    ![Task B](assets/images/task_b.png)

    ## Subtask B: Image Style Transfer Model Retrieval

    In this subtask, we tackle the problem of retrieving image style transfer models that produce a desired style.

    ### Background
    As the number of style-transfer models grows, users face the challenge of selecting a model that best reproduces a desired style. Testing every model is time-consuming.

    ### Problem Definition
    Given a single query image that exemplifies the target style, rank pre-trained style-transfer models by their predicted ability to reproduce that style.

    Let $\mathcal{M}=\{m_{1},m_{2},...,m_{K}\}$ be a set of candidate style-transfer models, and let $x \in \mathcal{X}$ be a query image exhibiting the target style. Rank candidate models in descending order of suitability.

    ### Participant Requirements
    * Develop a retrieval method that retrieves a style-transfer model capable of reproducing the style of a given query image.
    * For each test query, submit a full ranking of all candidate models.

    ### Evaluation
    Retrieval performance is measured by **Mean Reciprocal Rank (MRR)** and **nDCG@k**.
