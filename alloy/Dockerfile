
FROM alpine AS builder
# Copy config safely, adjust ownership if needed
COPY config.alloy /config.alloy

FROM grafana/alloy:latest
COPY --from=builder /config.alloy /etc/alloy/config.alloy
CMD ["run", "/etc/alloy/config.alloy"]

