FROM python:3.7.4-slim-buster
RUN apt-get update \
&& apt-get -y install \
    git \
    nodejs \
    npm \
&& python3 -m pip --no-cache-dir install pip -U \
&& python3 -m pip --no-cache-dir install \
    jupyter \
    jupyterlab \
    numpy \
    pandas \
    matplotlib \
    joblib \
    cython \
    scikit-learn \
    nltk \
    seaborn \
    featuretools \
    theano \
    keras \
    pybrain \
    plotly \
    gensim \
    statsmodels \
    bokeh \
    lightgbm \
    catboost \
    eli5 \
    lime \
    shap \
    spacy \
    torch==1.2.0+cpu torchvision==0.4.0+cpu -f https://download.pytorch.org/whl/torch_stable.html \
&& jupyter labextension install @jupyterlab/git @jupyterlab/dataregistry-extension \
&& jupyter labextension enable jupyterlab_git \
&& jupyter labextension enable dataregistry-extension \
&& rm -rf /var/lib/apt/lists/* \
mkdir notebooks \
WORKDIR /notebooks
VOLUME /notebooks
ENTRYPOINT jupyter lab --no-browser --ip=0.0.0.0 --notebook-dir=/notebooks --allow-root
EXPOSE 8888
