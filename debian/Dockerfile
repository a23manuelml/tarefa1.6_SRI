FROM debian:12

RUN apt update && apt install -y net-tools procps most iproute2  iputils-ping dnsutils

# Crea la carpeta para el archivo de configuración rndc
RUN mkdir -p /etc/bind

# Copia el archivo rndc.key y rndc.conf al contenedor
COPY rndc.key /etc/bind/rndc.key
COPY rndc.conf /etc/bind/rndc.conf

RUN apt clean && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["tail", "-f", "/dev/null"]



