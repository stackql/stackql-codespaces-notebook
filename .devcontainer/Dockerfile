FROM stackql/stackql-jupyter-base:latest AS stackql-jupyter
WORKDIR /jupyter
USER root
RUN mkdir -p /home/jovyan/.jupyter
COPY .devcontainer/jupyter_lab_config.py /home/jovyan/.jupyter/jupyter_lab_config.py
RUN chown -R jovyan:users /home/jovyan
# # copy example notebooks to Jupyter workspace
# COPY ./notebooks/* /jupyter
# RUN chmod 644 *.ipynb && \
#     chown jovyan:users *.ipynb
# # create directory for service account keys
# RUN mkdir -p /jupyter/.keys
# RUN chmod 644 /jupyter/.keys && \
#     chown jovyan:users /jupyter/.keys  
# # copy config directory
# RUN mkdir -p /config
# COPY config/ /config/
# # copy assets directory
# RUN mkdir -p /jupyter/assets
# COPY assets/ /jupyter/assets/
# RUN chown -R jovyan:users /jupyter/assets
# # copy entrypoint script
# RUN mkdir -p /scripts
# COPY scripts/ /scripts/
# RUN chmod +x /scripts/entrypoint.sh