FROM ubuntu:latest
RUN apt-get update && apt-get install -y openssh-server

# Política 1: Crear usuarios específicos
RUN useradd -m -s /bin/bash auditor
RUN useradd -m -s /bin/bash admin_red

# Política 2: Asignar contraseñas complejas (Usamos chpasswd correctamente)
RUN echo 'auditor:Aud1t0r_2026!' | chpasswd
RUN echo 'admin_red:Adm1n$R3d_Secure' | chpasswd

# Evitar acceso root directo
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin no/' /etc/ssh/sshd_config

CMD ["/usr/sbin/sshd", "-D"]