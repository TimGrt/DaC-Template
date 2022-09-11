FROM python:3-slim

WORKDIR /tmp

# Install package dependencies and clean up afterwards
RUN apt-get update \
 && apt-get install --no-install-recommends -y python3-cffi python3-brotli libpango-1.0-0 libpangoft2-1.0-0 chromium git\
 && apt-get autoremove \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# Copy .git folder for git-revision-date-localized-plugin
COPY .git .git

# Copy Python packages/dependencies file
COPY dockerfiles/pdf/requirements.txt .

# Update pip and install Python dependencies
RUN python3 -m pip install --no-cache-dir -U pip
RUN python3 -m pip install --no-cache-dir -r requirements.txt

# Copy documentation source files to working directory
COPY docs docs
COPY dockerfiles/pdf/mkdocs.yml .

# Build new documentation
RUN ENABLE_PDF_EXPORT=1 mkdocs build

EXPOSE 80

# Run webserver
CMD python -m http.server 80 -d site/