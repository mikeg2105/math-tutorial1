FROM sagemath/sagemath

MAINTAINER Erik M. Bray <erik.bray@lri.fr>

RUN ["mkdir", "notebooks"]
COPY notebooks/*.ipynb notebooks/



ARG SAGE_BRANCH=master
EXPOSE 8888

ENTRYPOINT sage -n jupyter --no-browser --ip=$(grep `hostname` /etc/hosts | cut -f1) --port=8888
