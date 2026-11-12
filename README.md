# Company Shadowrocket routing rules

Public routing rules for Shadowrocket. This repository contains **no node credentials**, UUIDs, keys, or server addresses.

- File: `company-vpn-shadowrocket-rules.conf`
- Domestic / private networks go DIRECT; listed IP-check sites and other foreign traffic go through the currently selected node.

## Import in Shadowrocket

1. Add your personal node first (scan your own node QR; do not share it).
2. Scan the rules QR, or in Shadowrocket go to **Config → + → Download from URL** and paste:

   `https://cdn.jsdelivr.net/gh/ikennychoi/company-shadowrocket-rules@main/company-vpn-shadowrocket-rules.conf`

3. Tap the downloaded config and choose **Use Configuration**.
4. Select your personal node, then connect.

If jsDelivr is slow to update after a change, the same file is also at:

`https://raw.githubusercontent.com/ikennychoi/company-shadowrocket-rules/main/company-vpn-shadowrocket-rules.conf`
