FROM alpine:3.22.0

RUN apk update; \
  apk add nginx curl tcpdump netcat-openbsd

ENTRYPOINT [ "/bin/sh", "-c", "trap 'echo Shutting down; exit 0' SIGTERM SIGINT SIGKILL; echo starting...; for i in \"$@\";  do exec $i & done;  sleep infinity & wait", "--" ]
