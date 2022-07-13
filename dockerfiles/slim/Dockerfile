FROM python:3.9-slim

WORKDIR /tmp

# Copy Python packages/dependencies file
COPY dockerfiles/slim/requirements.txt .

# Update pip and install Python dependencies
RUN python3 -m pip install --no-cache-dir -U pip
RUN python3 -m pip install --no-cache-dir -r requirements.txt

# Copy documentation source files to working directory
COPY docs docs
COPY dockerfiles/slim/mkdocs.yml .

# Build new documentation
RUN mkdocs build

EXPOSE 80

# Run webserver
CMD python -m http.server 80 -d site/
