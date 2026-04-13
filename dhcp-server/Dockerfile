FROM ubuntu:latest
RUN apt-get update && apt-get install -y isc-dhcp-server
COPY dhcpd.conf /etc/dhcp/dhcpd.conf
RUN sed -i 's/INTERFACESv4=""/INTERFACESv4="eth0"/g' /etc/default/isc-dhcp-server
RUN mkdir -p /var/lib/dhcp && touch /var/lib/dhcp/dhcpd.leases
CMD ["/usr/sbin/dhcpd", "-4", "-f", "-d", "--no-pid", "eth0"]