# Use an official Python runtime as a parent image
FROM python:3.10

# Install Poetry
RUN set -xe && \
    curl -sSL https://install.python-poetry.org | python3 - && \
    echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc

# Update PATH for poetry
ENV PATH="/root/.local/bin:$PATH"

# Verify Poetry installation
RUN poetry --version

# Set up the working directory
WORKDIR /app

# Copy the application code into the container
COPY . /app

# Install dependencies using Poetry
RUN poetry install

# Expose the application's port
EXPOSE 8000

# Start the application
CMD ["bash", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000"]

