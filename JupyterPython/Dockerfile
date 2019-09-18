FROM alpine:latest
RUN apk update \
&& apk add \
    ca-certificates \ 
    libstdc++ \
    python3 \
    zeromq-dev \
    && apk add --virtual=build_dependencies \
    cmake \
    gcc \
    g++ \
    make \
    musl-dev \
    python3-dev \
    linux-headers \
    freetype-dev \
    libpng-dev \
    openblas-dev \
    gfortran \
&& ln -s /usr/include/locale.h /usr/include/xlocale.h \
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
#RUN ATLAS=/usr/lib/openblas/lib/libopenblas.so LAPACK=/usr/lib/openblas/lib/libopenblas.so python3 -m pip --no-cache-dir install scipy \
#&& python3 -m pip --no-cache-dir install cython -U \
&& jupyter serverextension enable --py jupyterlab --sys-prefix \
&& apk del --purge -r build_dependencies \
&& rm -rf /var/cache/apk/* \
&& mkdir /notebooks
VOLUME /notebooks
ENTRYPOINT /usr/bin/jupyter lab --no-browser --ip=0.0.0.0 --notebook-dir=/notebooks --allow-root
EXPOSE 8888
