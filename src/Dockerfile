FROM krishnasrinivas/wetty:latest
LABEL maintainer="federicojasson@gmail.com"

EXPOSE 80
VOLUME /root/.ssh

# Workaround to force Wetty to listen on port 80
RUN sed -i "s/process.getuid() == 0/false/g" app.js

ENTRYPOINT ["sh", "-c"]
CMD ["node app.js -p 80 --sshhost ${SSH_HOST} --sshport ${SSH_PORT} --sshuser ${SSH_USER}"]
