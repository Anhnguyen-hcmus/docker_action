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
RUN conda env create -f /tmp/env.yml

RUN ln -s /opt/conda/envs/Humman_v4.0.0.alpha/bin/humann /usr/local/bin/humann

SHELL ["/bin/bash", "-c"]

CMD ["conda", "run", "-n", "Humman_v4.0.0.alpha", "humann", "--version"]

#2