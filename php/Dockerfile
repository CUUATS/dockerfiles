FROM php:5.6-apache

# Install software.
RUN apt-get update && apt-get install -y --no-install-recommends ssmtp

# Change ssmtp settings.
RUN sed -ri -e 's/^(mailhub=).*/\1smtp/' \
    -e 's/^#(FromLineOverride)/\1/' /etc/ssmtp/ssmtp.conf

# Configure PHP to use ssmtp.
RUN echo "sendmail_path=sendmail -i -t" >> /usr/local/etc/php/conf.d/php-sendmail.ini
