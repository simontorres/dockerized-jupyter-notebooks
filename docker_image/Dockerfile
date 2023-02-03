FROM python:3.9
RUN apt-get update && apt-get clean && pip install --upgrade pip
RUN useradd -ms /bin/bash simon
# USER simon
WORKDIR /home/simon
ENV PATH="/home/simon/.local/bin:${PATH}"
RUN mkdir -p /home/simon/jupyter/notebooks
COPY requirements.txt /home/simon/jupyter
RUN pip install -r jupyter/requirements.txt
RUN jupyter contrib nbextension install
USER simon
# CMD ['jupyter', 'notebook', '--no-browser', '--ip=0.0.0.0']
