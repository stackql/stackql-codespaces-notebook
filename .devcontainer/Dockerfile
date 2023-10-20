FROM stackql/stackql:latest AS stackql
FROM mcr.microsoft.com/devcontainers/universal:2
COPY --from=stackql /srv/stackql/stackql /usr/local/bin/stackql
# set up matplotlib temp dir
RUN mkdir -p /tmp/matplotlib
RUN chmod 777 /tmp/matplotlib
ENV MPLCONFIGDIR=/tmp/matplotlib
ENV PYDEVD_DISABLE_FILE_VALIDATION=1
ENV PYTHON_PACKAGES="\
    pystackql \
    matplotlib \
    pandas \
	mplfinance \
    psycopg2-binary \
    nest_asyncio \
    plotly \
    ipytree \
    nbformat \
    networkx \
" 
RUN pip install --upgrade pip \
    && pip install --no-cache-dir $PYTHON_PACKAGES