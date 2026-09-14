FROM continuumio/miniconda3:latest

ENV CONDA_ENV=fragmentomics-task1
ENV PATH=/opt/conda/envs/${CONDA_ENV}/bin:/opt/conda/bin:${PATH}

COPY env.yml /tmp/env.yml

# Install mamba in the base environment and create the environment from env.yml.
RUN conda install --yes --quiet -n base -c conda-forge mamba \
	&& mamba env create --file /tmp/env.yml \
	&& conda clean --all --yes \
	&& rm -f /tmp/env.yml

# Fail the image build if the declared runtime is incomplete.
RUN python --version \
	&& samtools --version \
	&& nextflow -version \
	&& python -c "import matplotlib, numpy, pandas, pysam, seaborn; print('Python packages: OK')"

WORKDIR /workspace

CMD ["bash"]