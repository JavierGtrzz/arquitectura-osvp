FROM ubuntu:latest
RUN apt-get update && apt-get install -y openssh-server

# Política 1: Crear usuarios específicos
RUN useradd -m -s /bin/bash auditor
RUN useradd -m -s /bin/bash admin_red

# Política 2: Asignar contraseñas complejas (Usamos chpasswd correctamente)
RUN echo 'auditor:ksadfhakdhjsahoiu4' | chpasswd
RUN echo 'admin_red:#ksadfhakdhjsahoiu4' | chpasswd

# Evitar acceso root directo
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin no/' /etc/ssh/sshd_config

CMD ["/usr/sbin/sshd", "-D"]