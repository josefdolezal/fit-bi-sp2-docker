FROM php:7.1-rc-alpine

# Install ApiGen
RUN curl -L -O https://github.com/ApiGen/ApiGen.github.io/raw/master/apigen.phar
RUN mv apigen.phar /usr/local/bin/apigen
RUN chmod +x /usr/local/bin/apigen

CMD ["apigen", "generate", "-s", "/app/src", "-d", "/app/docs", "--template-theme", "bootstrap"]
