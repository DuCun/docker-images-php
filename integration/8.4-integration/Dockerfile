FROM xiaomoy/php:8.4-fpm

RUN set -eux; \
    apt-get update \
    && apt-get install -y supervisor cron \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY ./docker-integration.conf /etc/supervisor/conf.d/

RUN chmod -R 644 /etc/supervisor/conf.d/*.conf

CMD ["supervisord","-c","/etc/supervisor/supervisord.conf","-n"]
