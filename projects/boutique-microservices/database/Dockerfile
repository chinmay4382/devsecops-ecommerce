FROM postgres:15-alpine

ENV POSTGRES_DB=boutique_db \
    POSTGRES_USER=postgres \
    POSTGRES_PASSWORD=postgres123 \
    POSTGRES_MULTIBYTE=auth_db,products_db,orders_db,users_db

COPY init/ /docker-entrypoint-initdb.d/

RUN chmod +x /docker-entrypoint-initdb.d/*.sh

HEALTHCHECK --interval=30s --timeout=10s --retries=5 \
    CMD pg_isready -U postgres

EXPOSE 5432
