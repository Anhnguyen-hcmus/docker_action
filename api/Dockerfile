# ##bowtie_2.5.4 Dockerfile
# FROM continuumio/miniconda3

# COPY env.yml /tmp/env.yml
# RUN conda env create -f /tmp/env.yml

# RUN ln -s /opt/conda/envs/bowtie_2.5.4/bin/bowtie2 /usr/local/bin/bowtie2
# RUN ln -s /opt/conda/envs/bowtie_2.5.4/bin/samtools /usr/local/bin/samtools
# RUN ln -s /opt/conda/envs/bowtie_2.5.4/bin/bedtools /usr/local/bin/bedtools

# SHELL ["/bin/bash", "-c"]

# CMD ["conda", "run", "-n", "bowtie_2.5.4", "bowtie2", "--version"]

# ##updating samtools and bedtools -2
# ##bowtie_2.5.4 Dockerfile
# FROM continuumio/miniconda3

# COPY env.yml /tmp/env.yml
# RUN conda env create -f /tmp/env.yml

# RUN ln -s /opt/conda/envs/MGPipe/bin/kraken2 /usr/local/bin/kraken2
# RUN ln -s /opt/conda/envs/MGPipe/bin/bracken /usr/local/bin/bracken
# RUN ln -s /opt/conda/envs/MGPipe/bin/kraken-biom /usr/local/bin/kraken-biom
# RUN ln -s /opt/conda/envs/MGPipe/bin/humann /usr/local/bin/humann
# RUN ln -s /opt/conda/envs/MGPipe/bin/diamond /usr/local/bin/diamond
# RUN ln -s /opt/conda/envs/MGPipe/bin/humann_config /usr/local/bin/humann_config
# RUN ln -s /opt/conda/envs/MGPipe/bin/glpsol /usr/local/bin/glpsol

# SHELL ["/bin/bash", "-c"]

# CMD ["conda", "run", "-n", "MGPipe", "glpsol", "--version"]

# ##updating samtools and bedtools -2
##humann Dockerfile
FROM continuumio/miniconda3

COPY env.yml /tmp/env.yml

# show env.yml in build log for debugging
RUN echo "---- env.yml ----" && cat /tmp/env.yml && echo "---- end env.yml ----"

# install mamba and create env (mamba first; fallback to conda with --debug)
RUN conda install -n base -c conda-forge mamba -y && \
    mamba env create -f /tmp/env.yml -y || (echo "mamba failed, trying conda (debug)" && conda env create -f /tmp/env.yml --debug)

# create safe symlinks (ignore if not present)
RUN ln -s /opt/conda/envs/Humman_v4.0.0/bin/humann /usr/local/bin/humann || true
RUN ln -s /opt/conda/envs/Humman_v4.0.0/bin/glpsol /usr/local/bin/glpsol || true
RUN ln -s /opt/conda/envs/Humman_v4.0.0/bin/diamond /usr/local/bin/diamond || true
RUN ln -s /opt/conda/envs/Humman_v4.0.0/bin/humann_config /usr/local/bin/humann_config || true
RUN ln -s /opt/conda/envs/Humman_v4.0.0/bin/metaphlan /usr/local/bin/metaphlan || true

SHELL ["/bin/bash", "-c"]
CMD ["conda", "run", "-n", "Humman_v4.0.0", "metaphlan", "--version"]

#7