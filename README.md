# ansible-role-systemd-resolved
Ansible role configures SystemD Network Name Resolution manager

# Usage
```yaml
---
# List of IPv4 and IPv6 addresses to use as system DNS servers.
# This setting defaults to the empty list.
systemd_resolved_dns: null

# List of IPv4 and IPv6 addresses to use as the fallback DNS servers.
# If this option is not given, a compiled-in list of DNS servers is used instead.
systemd_resolved_fallback_dns: null

# List of domains, optionally prefixed with "~".
# Defaults to the empty list.
systemd_resolved_domains: null

# Takes a boolean argument or "allow-downgrade".
# If set to "allow-downgrade", DNSSEC validation is attempted,
# but if the server does not support DNSSEC properly, DNSSEC mode is automatically disabled.
# Defaults to false.
systemd_resolved_dnssec: null

# Takes a boolean argument or "opportunistic".
# When set to "opportunistic" DNS request are attempted to send encrypted with DNS-over-TLS.
# If the DNS server does not support TLS, DNS-over-TLS is disabled.
# Defaults to false.
systemd_resolved_dns_over_tls: null

# Controls Multicast DNS support (RFC 6762[3]) on the local host.
# Takes a boolean argument or "resolve".
# If set to "resolve", only resolution support is enabled, but responding is disabled.
systemd_resolved_multicast_dns: null

# Controls Link-Local Multicast Name Resolution support (RFC 4795[2]) on the local host.
# Takes a boolean argument or "resolve".
# If set to "resolve", only resolution support is enabled, but responding is disabled.
systemd_resolved_llmnr: null

# Takes a boolean or "no-negative" as argument.
# If "no-negative", only positive answers are cached.
# Defaults to true.
systemd_resolved_cache: null

# Takes a boolean as argument.
# If "no" (the default), and response cames from host-local IP address (such as 127.0.0.1 or ::1),
# the result wouldn't be cached in order to avoid potential duplicate local caching.
systemd_resolved_cache_from_localhost: null

# Takes a boolean argument or one of "udp" and "tcp
systemd_resolved_dns_stub_listener: null

# List IPv4 or IPv6 address to listen on.
# Defaults to the empty list.
systemd_resolved_dns_stub_listener_extra: null

# Takes a boolean argument.
# Defaults to true.
systemd_resolved_read_etc_hosts: null

# Takes a boolean argument.
# Defaults to true.
systemd_resolved_resolve_unicast_single_label: null

# Takes a duration value, which determines the length of time DNS resource records
#  can be retained in the cache beyond their Time To Live (TTL).
# This allows these records to be returned as stale records.
# By default, this value is set to zero, meaning that DNS resource records
# are not stored in the cache after their TTL expires.
systemd_resolved_stale_retention_sec: null

# Specifies the target path for the symbolic link "/etc/resolv.conf"
# Defaults to "/run/systemd/resolve/stub-resolv.conf"
systemd_resolved_resolv_conf_link_target: /run/systemd/resolve/stub-resolv.conf

# Specifies drop-ins.
# Drop-in format:
# - name: example  # File name
#   weight: 60     # File name prefix (60-example.conf)
#   state: present # Default - present
#   dns: 127.0.0.1
systemd_resolved_dropins: []
```
