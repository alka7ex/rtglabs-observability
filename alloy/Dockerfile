FROM alpine AS builder
COPY config.alloy /config.alloy

FROM grafana/alloy:latest

# Use root for setup
USER root

# Copy config to Alloy's config path
COPY --from=builder /config.alloy /etc/alloy/config.alloy

# Adjust ownership if Alloy expects a specific UID (e.g., 10001)
RUN chown 10001:10001 /etc/alloy/config.alloy

# Drop back to Alloy's user (usually 10001) if needed
USER 10001

# Start Alloy
CMD ["run", "/etc/alloy/config.alloy"]
