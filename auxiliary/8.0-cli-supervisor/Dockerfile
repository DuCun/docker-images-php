FROM xiaomoy/php:8.0-cli

RUN set -eux; \
    apt-get update \
    && apt-get install -y supervisor \
    && rm -rf /var/lib/apt/lists/*

CMD ["supervisord","-c","/etc/supervisor/supervisord.conf","-n"]
