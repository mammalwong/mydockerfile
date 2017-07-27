FROM andyshinn/dnsmasq

RUN ln -s /usr/sbin/dnsmasq /usr/sbin/dockerdns

ENTRYPOINT ["dockerdns", "-k"]
