FROM postgres:13

# Install build tools and PostgreSQL development headers
RUN apt-get update && apt-get install -y \
    postgresql-server-dev-13 \
    build-essential \
    git && \
    # Clone and build pgvector
    git clone https://github.com/pgvector/pgvector.git && \
    cd pgvector && \
    make && \
    make install && \
    cd .. && rm -rf pgvector && \
    # Cleanup build dependencies
    apt-get remove -y postgresql-server-dev-13 build-essential git && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/*
