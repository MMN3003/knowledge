curl -o /dev/null -s -w '  
DNS Lookup: %{time_namelookup}s  
TCP Connect: %{time_connect}s  
TLS Handshake:%{time_appconnect}s  
TTFB: %{time_starttransfer}s  
Total Time: %{time_total}s  
Download Size: %{size_download} bytes  
Speed: %{speed_download} bytes/s  
\n' https://sarmayex.com