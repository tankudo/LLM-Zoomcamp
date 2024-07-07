# Course Module

## Table of Contents
- [Open Source LLMs](#lecture-1)
- [Using SaturnCloud for GPU Notebooks](#lecture-2)
- [HuggingFace and Google FLAN T5](#lecture-3)
- [](#lecture-4)
- [](#lecture-5)
- [](#lecture-6)
- [](#lecture-7)
- [](#lecture-8)
- [](#lecture-9)
---

<details>
  <summary id="lecture-1"> Open Source LLMs</summary>

## Introduction
- **Module Focus:** In this module, will explored  open-source LLMs - alternatives to OpenAI.

## Open Source LLMs
- **Control:** These models can be executed on our own hardware, giving us full control.

## Model Options
- **Diverse Models:** There are numerous open-source models available, including well-known ones and many others.
- **Examples:**
  - **LLaMA:** Developed by Meta (Facebook).
  - **Flan-T5 or T5:** Developed by Google.
  - **Mistral:** Another notable model with an accessible API.

## Practical Implementation
- **Running Models:** We will cover how to run these models, typically requiring a GPU.
- **Environment Setup:** Discussion on setting up the proper environment for running these models.

## Workflow Adaptation
- **Replacing Components:** We'll explore how to replace parts of the workflow with different models.
- **Focus:** Setting up environments and utilizing different LLMs effectively.

## Hands-On Practice
- **Flan-T5 Example:** We'll delve into specific models like Flan-T5.
- **Model Access:** How to access models from platforms like Hugging Face Hub.

## Conclusion
- **Exciting Module:** This module promises to be interesting and informative.
- **Next Steps:** In the next module, we will see how to get a notebook with a GPU to run these models.

See you soon!


</details>

<details>
  <summary id="lecture-2"> Using SaturnCloud for GPU Notebooks</summary>

## Introduction
- **Objective:** Ler's use Saturn Cloud to get a notebook with a GPU, essential for running open-source LLMs.

## Why GPU?
- **GPU Requirement:** Most open-source LLMs require a GPU for efficient performance.
- **Saturn Cloud:** One of the possible options for setting up a GPU environment.

## Alternative Options
- **Google Colab**
- **Google Cloud Platform**
- **AWS SageMaker**
- **Other Cloud Services**

## Saturn Cloud Setup
1. **Login:**
   - Log in to Saturn Cloud if you already have an account.
   - If you do not have an account, you can sign up and get extra GPU hours by filling out a form on the course management platform or requesting a technical demo.

2. **Creating a Notebook:**
   - **Log in:** Log in using your credentials.
   - **Create Notebook:** Go to the notebook creation section in Saturn Cloud.
   - **Secrets:** Add necessary tokens like OpenAI or Hugging Face tokens in the secrets section.
   - **SSH Keys:** Set up Git access by adding your public SSH key to GitHub for easy access to repositories.

3. **Configuring the Environment:**
   - **Notebook Server:** Create a new notebook server.
   - **Starter Notebook:** Use the provided starter notebook for the course.
   - **Environment Setup:** Choose the appropriate Python version and environment. Install necessary packages like `transformers`, `accelerate`, and `bitsandbytes`.

4. **Running the Notebook:**
   - **Install Packages:** Install the required libraries and clone the course repository.
   - **Start Notebook:** Launch the Jupyter Notebook or JupyterLab interface.
   - **Execute Code:** Run the starter code provided in the notebook.

5. **Environment Verification:**
   - **Check GPU:** Verify the presence of a GPU using the `nvidia-smi` command.
   - **Ready to Use:** Ensure the environment is correctly set up and ready for running LLMs.

## Next Steps
- **Upcoming Videos:** Learn how to use this environment to run Google's Flan-T5 model, an open-source LLM.
- **Hands-On Practice:** Continue with practical exercises to solidify your understanding.

</details>

<details>
  <summary id="lecture-3">  HuggingFace and Google FLAN T5</summary>

## Introduction  
- The first open-source LLM is from Google, accessed via the Hugging Face library.
- Brief overview of Hugging Face:
  - A repository for models where various companies, including Google, publish their models.
  - Known for the Hugging Face Hub, a central place for finding and downloading models.

## About Hugging Face
- Hugging Face hosts models which can be uploaded and downloaded.
- Trending models can be found on this website.
- Models are not limited to LLMs; various types of models are available.
- Hugging Face Hub is a repository familiar to GitHub but for models.

## Using Hugging Face Hub
- We will use the Google Flan-T5 XL model.
- The Hugging Face library, 'Transformers,' is used to fetch and run models.
- Here is also good demonstration of finding and accessing model documentation and examples on Hugging Face Hub.
```python
from transformers import T5Tokenizer, T5ForConditionalGeneration

tokenizer = T5Tokenizer.from_pretrained("google/flan-t5-xl")
model = T5ForConditionalGeneration.from_pretrained("google/flan-t5-xl", device_map="auto") # actual model
```

## Downloading Model Files
- Hugging Face Hub helps fetch necessary model files via the Transformers library.
- Importance of setting the appropriate file download location to manage space.

## Setting up the Environment
- Importance of sufficient space for downloading large model files.
- Execution and testing of the setup using a sample model.
```python
tokenizer = T5Tokenizer.from_pretrained("google/flan-t5-xl", cache_dir='/run/cache/huggingface')
model = T5ForConditionalGeneration.from_pretrained("google/flan-t5-xl", cache_dir='/run/cache/huggingface', device_map="auto")
```

## Importing and Using the Model
- Explanation of importing necessary components: the generator and tokenizer.
```python
input_ids = tokenizer(prompt, return_tensors="pt").input_ids.to("cuda")
outputs = model.generate(input_ids, )
result = tokenizer.decode(outputs[0])
```

##  Generating Responses
- Using parameters like `max_length` to control the length of generated responses.
```python
outputs = model.generate(
        input_ids,
        max_length=generate_params.get("max_length", 100),
        num_beams=generate_params.get("num_beams", 5),
        do_sample=generate_params.get("do_sample", False),
        temperature=generate_params.get("temperature", 1.0),
        top_k=generate_params.get("top_k", 50),
        top_p=generate_params.get("top_p", 0.95),
    )
```

## Summary
- Transition from using OpenAI to a local GPU instance.
- Benefits of running models locally.
- Introduction to exploring other models, such as Microsoft's T3, in future videos.

---

**Links:**
- [Hugging Face Hub](https://huggingface.co/)
- [Google Flan T5 XL Model Documentation](https://huggingface.co/google/flan-t5-xl)

</details>

<details>
  <summary id="lecture-4"> </summary>

</details>

<details>
  <summary id="lecture-5"> </summary>

</details>

<details>
  <summary id="lecture-6"> </summary>

</details>

<details>
  <summary id="lecture-7"> </summary>

</details>

<details>
  <summary id="lecture-8"> </summary>

</details>

<details>
  <summary id="lecture-9"> </summary>

</details>
