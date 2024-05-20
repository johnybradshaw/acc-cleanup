FROM alpine:latest

# Update the base image
RUN apk update && apk upgrade

# Install necessary dependencies
RUN apk add --no-cache python3 py3-pip jq

# Create a virtual environment
RUN python3 -m venv /venv
ENV PATH="/venv/bin:$PATH"

# Install the Linode CLI in the virtual environment
RUN pip3 install linode-cli

# Set the entrypoint to the Linode CLI
ENTRYPOINT ["linode-cli"]

# Expect the Linode API token to be provided as an environment variable
ENV LINODE_CLI_TOKEN=""