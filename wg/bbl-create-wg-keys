#!/bin/bash

if [[ $# -ne 1 ]]; then
  echo "Usage: $0 <name>"
  exit 1
fi

name=$1
keys_dir="/etc/wireguard"

# Generate private key
private_key=$(wg genkey)

# Derive public key from private key
public_key=$(echo "$private_key" | wg pubkey)

# Save keys to files
echo "$private_key" > "$keys_dir/$name"
echo "$public_key" > "$keys_dir/$name.pub"

# Display hostname and keys
hostname=$(hostname)
echo "Hostname: $hostname"
echo "pubkey $public_key"
echo "privkey $private_key"

