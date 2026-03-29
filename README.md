This Terraform creates Azure Windows VMs with direct RDP access.

What changed:
- Each VM gets its own static public IP.
- An NSG allows inbound TCP 3389 so you can connect even if your local IP changes.
- Terraform outputs the public IPs and `ip:3389` targets after apply.

Usage:
- Run `terraform apply`.
- Use the `rdp_public_ips` or `rdp_targets` outputs to connect with Remote Desktop.

Security note:
- This is convenient but not hardened. Opening RDP to `*` is suitable for testing only.
- For safer long-term access, use Azure Bastion or restrict the NSG rule to trusted source ranges.