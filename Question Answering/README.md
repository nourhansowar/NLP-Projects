# Question Answering system using a Pre-trained Bert based model 💬

Question-answering models can retrieve the answer to a question from a given text, which is useful for searching for an answer in a document. <br> Some question-answering models can generate answers without context! (Hugging Face)
<h2>Types of Question Answering Models</h2>
<ul>
<li>Extractive Question Answering 
<li>Open Generative Question Answering 
<li>Closed Generative Question Answering 
</ul>


<h2>Dataset Overview</h2>
The question-answering system in this project is evaluated using the Stanford Question Answering Dataset <code>(SQUAD)</code>. <br>SQUAD is a widely used benchmark dataset for evaluating machine reading comprehension and question-answering systems.<br>
The SQUAD dataset contains a diverse set of passages from a variety of topics and genres.
<br>
<h3>Each example in the dataset consists of the following components:</h3>
<ul>
<li>Context Paragraph: A corpus that contains the information from which the answer can be extracted.
<li>Question: A question related to the context, formulated to prompt the model to extract the relevant answer.
<li>Answer Span: The exact span of text within the context paragraph that serves as the answer to the question.
</ul>
The dataset can be found here: <a href= "https://huggingface.co/datasets/squad">SQuAD link</a>

<h2>Setup Instructions</h2>
<h3>Requirements:</h3>
<ul>
    <li>Python version => 3.6 is recommended
    <li>Operating System: Windows
</ul>

<h3>Python Packages Required: </h3>
<ul> 
    <li>
        datasets==2.14.4
    <li>
        numpy==1.24.4
    <li>
        pandas==2.0.3
    <li>
        tokenizers==0.13.3
    <li>
        torch==2.0.1
    <li>
        transformers
    <li>
        import torch
    <li>
        pytest

</ul>

<h2>Model and Question Answering System</h2>
<ul>
<li>Model used:
    <ul>
        <li><b>Model name: <code>'distilbert-base-cased-distilled-squad'</b></code> - a variant of the DistilBERT model that has been fine-tuned specifically for the SQuAD. This model is designed to accurately extract answers from a given context.</li>
    </ul>
<li>How the System Works:
    <ul>
    Our Question Answering system takes a context paragraph and a question as inputs and aims to extract relevant answers from the context.<br>
    Using multiple steps:
        <li><code>Tokenization:</code>  The system takes a question and a context as input, then the context paragraph and question are tokenized into subword tokens using the tokenizer provided by the Hugging Face Transformers library of AutoModelForQuestionAnswering. 
        <li><code>Process input through the model:</code> The tokenized inputs are passed through the distilbert-base-cased-distilled-squad model. This model has been fine-tuned on the squad dataset.
        <li><code>Extract the answer span:</code> The model's output consists of logits (probabilities) for each token in the context paragraph. The tokens with the highest start and end logits are to the beginning and end of the answer span within the context.
    </ul>
</ul>


