# CV Job Matching using Doc2Vec

This repository contains a job matching system that utilizes Doc2Vec to match CVs (resumes) with job postings. The system aims to automate the process of finding suitable job candidates by analyzing the similarity between CVs and job descriptions.

## Repository Structure

The repository is organized as follows:

- **CV folder**: This folder contains the CVs (resumes) of job candidates. It serves as the input for the matching algorithm.

- **dataset folder**: This folder contains the job postings dataset used to train the Doc2Vec model. The dataset includes various job descriptions to create embeddings for comparison.

- **Matching_algorithm.ipynb**: This Jupyter Notebook file contains the code for training the Doc2Vec model and performing the CV-job matching. It provides an end-to-end solution for generating the model and evaluating its performance.

- **cv_job_matching.model**: This file is the trained model generated by the matching algorithm. It encapsulates the embeddings and other relevant information necessary for performing CV-job matching.

- **requirements.txt**: This file lists all the dependencies and their respective versions required to run the matching algorithm and reproduce the results.

## Usage

To use this CV job matching system, follow the steps below:

1. Ensure you have the required dependencies installed. You can install them by running the following command:

   ```
   pip install -r requirements.txt
   ```

2. Place the CVs (resumes) of job candidates in the CV folder. Make sure the CVs are in a compatible format (e.g., PDF, DOCX, TXT) that can be processed by the matching algorithm.

3. Adjust the job postings dataset in the dataset folder according to your needs. It should include a collection of job descriptions in a format suitable for training the Doc2Vec model.

4. Open the `Matching_algorithm.ipynb` Jupyter Notebook. This notebook provides detailed instructions on how to train the Doc2Vec model using the dataset and perform the CV-job matching.

5. After executing the code in the notebook, the trained model will be saved as `cv_job_matching.model`.

6. You can now use the generated model (`cv_job_matching.model`) for CV-job matching. Load the model and apply it to new CVs to find the most suitable job postings.


   ```
   # Model evaluation
    model = Doc2Vec.load('cv_job_maching.model')
    v1 = model.infer_vector(input_CV.split()) # Input of CV
    v2 = model.infer_vector(input_JD.split()) # Input of JD
    similarity = 100*(np.dot(np.array(v1), np.array(v2))) / (norm(np.array(v1)) * norm(np.array(v2)))
    print(round(similarity, 2))
   ```
7. You will have the visualization for the matching percentage as well as notification as belows:
<img width="561" alt="Screenshot 2023-06-11 at 10 17 24 PM" src="https://github.com/kirudang/CV-Job-matching/assets/91911269/93041869-4641-4133-99f9-fd723acc89f5">


## License

The contents of this repository are licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code and accompanying files as needed.

## Acknowledgments

This CV job matching system was developed using the Doc2Vec algorithm and is inspired by the field of Natural Language Processing (NLP) and Information Retrieval (IR). We acknowledge the contributions of the open-source community and the libraries used in this project.
