# Paranoid

## Details

Author: Vlad Roskov (vos)

Added at 14:40 UTC: to save some guessing, flag is the current password. Flag format is still cybrics{...}, so you'll know when you find it.

My neighbors are always very careful about their security. For example they've just bought a new home Wi-Fi router, and instead of just leaving it open, they instantly are setting passwords!

Don't they trust me? I feel offended.

paranoid.zip

Can you give me their current router admin pw?

## Solve

Downloaded the attachment and unzip it got me a pcap file.

Looking it at first, I saw that it is a 802.11 challenge. So I poked around and saw that it is a pcap file containing WEP packets.

So what I would need to do first would be to decrypt it. So I tried using the following command but to no avail due to the lack of IV packets.

```bash
aircrack-ng -b "00:0c:43:30:52:88" -a 1 paranoid.pcap
```

So I spend some time figuring out what was sent before the WEP as they mentioned about the router being new and to my surprise there were packets being sent out in plain.

I then looked around and I finally saw a `POST /req/wlanApSecurity` in it, contains the field `WLAN_AP_WEP_KEY1` with the value `Xi1nvy5KGSgI2`.

I then executed the command below.

```bash
airdecap-ng -w "5869316e7679354b4753674932" paranoid.pcap
```

By doing so, got me a pcap with decrypted WEP packets. However, when I looked at it, there were still encrypted packets. I was confused for awhile until I tried to look for 'wpa' which found me a packet doing a `POST /req/wlanApSecurity` containing the field `WLAN_AP_WPA_PSK` with value `2_RGR_xO-uiJFiAxdA33-PsdanuK`.

I then decrypt the WPA packets with the key with the following command.

```bash
airdecap-ng -p '2_RGR_xO-uiJFiAxdA33-PsdanuK' -e 'NSA_WIFI_DONT_HACK' paranoid.pcap
```

After doing so, I just search for the key word 'cybric' which I found the flag in `POST /req/admin` with the field `ADMIN_NAME` and value `cybrics{n0_w4Y_7o_h1d3_fR0m_Y0_n316hb0R}`

```text
cybrics{n0_w4Y_7o_h1d3_fR0m_Y0_n316hb0R}
```

