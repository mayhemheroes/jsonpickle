FROM python:3.11-slim

RUN apt-get update && \
        DEBIAN_FRONTEND=noninteractive apt-get install -y git clang && \
        rm -rf /var/lib/apt/lists/*

RUN pip install atheris

# Build
ADD . /src
WORKDIR /src
RUN python3 -m pip install .

CMD ["/src/mayhem/fuzz_decode.py"]
