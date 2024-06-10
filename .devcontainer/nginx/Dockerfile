FROM nginx:alpine3.19

# Install openssl
RUN apk --no-cache add openssl

# Generate ssl certificate
RUN printf "ID\nID\nID\n\nnn\nnn\nlocalhost\nadmin@host.com\n" \
    | openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/self-signed.key -out /etc/ssl/self-signed.crt
