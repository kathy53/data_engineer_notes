FROM python:3.8

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY requirements.txt /usr/src/app/
RUN pip install --no-cache-dir -r requirements.txt
# comment the next line
RUN pip install jupyterlab
EXPOSE 8888
# comment the next two lines
RUN jupyter lab --generate-config
RUN echo "c.NotebookApp.token = ''" >> /root/.jupyter/jupyter_notebook_config.py
ENV PYTHONPATH "${PYTHONPATH}:/usr/src/app"
CMD ["jupyter", "lab","--no-browser","--allow-root","--ip=0.0.0.0"]
# CMD ["/bin/bash"]
