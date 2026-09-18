# Operations Checklist

A sanitized checklist for operating the DuzgunDev environment. It documents the process without exposing credentials, internal addresses, or production configuration.

## Before a deployment

- Review the Compose configuration and changed environment variables
- Confirm that no secrets are committed to version control
- Validate proxy labels, hostnames, and network assignments
- Check available disk space and recent backup status
- Record the intended change and rollback path

## After a deployment

- Confirm that all expected containers are running
- Review container logs for startup errors
- Test the public endpoint over HTTPS
- Verify authentication on protected services
- Check Prometheus targets and Grafana data
- Confirm availability checks in Uptime Kuma

## Backup verification

- Confirm that the scheduled backup job completed
- Review the backup log for errors
- Verify the generated SHA-256 manifest
- Check that databases, configuration, and required volumes are covered
- Perform periodic restoration tests in a separate environment

## Incident workflow

1. Identify the affected service and user-visible impact
2. Check container state, resource usage, logs, and recent changes
3. Isolate whether the issue belongs to DNS, proxy, authentication, networking, storage, or the application
4. Apply the smallest reversible fix
5. Verify service recovery and monitoring status
6. Document the cause, resolution, and preventive action

## Security rule

Production secrets, internal addresses, private logs, tokens, and backup contents are never published in this repository.
