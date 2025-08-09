# FROM python:3.9

# # Set the working directory in the container
# WORKDIR /usr/src/app

# # Copy the dependencies file to the working directory
# COPY requirements.txt ./

# # Install any needed packages specified in requirements.txt
# RUN pip install --no-cache-dir -r requirements.txt

# # Copy the content of the local src directory to the working directory
# COPY . .

# # Run the application
# CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]
FROM continuumio/miniconda3

COPY env.yml /tmp/env.yml
RUN conda env create -f /tmp/env.yml

RUN ln -s /opt/conda/envs/bowtie_2.5.4/bin/bowtie2 /usr/local/bin/bowtie2
RUN ln -s /opt/conda/envs/bowtie_2.5.4/bin/samtools /usr/local/bin/samtools
RUN ln -s /opt/conda/envs/bowtie_2.5.4/bin/bedtools /usr/local/bin/bedtools

SHELL ["/bin/bash", "-c"]

CMD ["conda", "run", "-n", "bowtie_2.5.4", "bowtie2", "--version"]

##updating samtools and bedtools -2