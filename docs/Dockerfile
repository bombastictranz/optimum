FROM nikolaik/python-nodejs:python3.11-nodejs23

ARG commit_sha
ARG clone_url

RUN apt -y update
RUN python3 -m pip install --no-cache-dir --upgrade pip
RUN python3 -m pip install --no-cache-dir git+https://github.com/huggingface/doc-builder.git

RUN git clone $clone_url && cd optimum && git checkout $commit_sha
RUN python3 -m pip install --no-cache-dir ./optimum[onnxruntime,benchmark,quality,doc-build,diffusers]
