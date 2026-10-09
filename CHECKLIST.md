# Linux server hardening checklist

Use this as a review worksheet alongside the [full guide](README.md). Record evidence and exceptions for your server; checking every box does not guarantee security or benchmark compliance.

## Before making changes

- [ ] Record the distribution, release, server purpose, exposed services, and administrator accounts.
- [ ] Confirm the OS release is supported and receives security updates.
- [ ] Back up configuration and data; test restoration separately from the production server.
- [ ] Confirm console/recovery access and keep a working SSH session open during access changes.
- [ ] Test changes in a disposable VM matching the target distribution and release.

## Access and network exposure

- [ ] Use individual administrator accounts and grant only needed sudo privileges.
- [ ] Protect SSH private keys and verify the server host-key fingerprint.
- [ ] Prove key login works before restricting password or root login.
- [ ] Run `sudo sshd -t` before reloading SSH; inspect effective settings with `sudo sshd -T` and account for `Match` rules.
- [ ] After reload, prove a fresh SSH login and required sudo access work.
- [ ] Inventory listening services with `sudo ss -tulpn`; remove unnecessary services.
- [ ] Permit the actual SSH port and required application traffic before enabling a firewall.
- [ ] Review IPv4, IPv6, cloud/network firewalls, and container-published ports; verify exposure from another host.

## Maintenance and detection

- [ ] Apply security updates and confirm the update policy, failure alerts, and reboot plan.
- [ ] Keep AppArmor or SELinux enabled where supplied; investigate denials before weakening policy.
- [ ] Confirm time synchronization and useful authentication/service logs.
- [ ] Send important logs off-host where practical and test alert delivery.
- [ ] Review security audit findings and document justified exceptions.
- [ ] Test backup restoration, including access to required encryption keys.
- [ ] Schedule periodic reviews of access, updates, exposed ports, and restore readiness.

## Change record

| Date | Control/change | Verification evidence | Rollback/recovery | Exception/owner |
| --- | --- | --- | --- | --- |
| YYYY-MM-DD | Describe the change | Record actual results | Record recovery steps | If applicable |

## References

- [Ubuntu OpenSSH server](https://ubuntu.com/server/docs/how-to/security/openssh-server/)
- [OpenSSH server manual](https://man.openbsd.org/sshd.8)
- [Ubuntu firewalls](https://ubuntu.com/server/docs/how-to/security/firewalls/)
- [Ubuntu security](https://ubuntu.com/server/docs/how-to/security/)
- [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks/)

This checklist is an addition to Rhett Bohling's adaptation. It uses the repository's [CC BY-SA 4.0 license](LICENSE.txt).
