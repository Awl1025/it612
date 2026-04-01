@Awl1025 ➜ /workspaces/it612/Awk_Participation (main) $ grep ' 200 ' log.txt
192.168.1.10 - - [01/Apr/2026:09:15:22] "GET /index.html" 200 1024
192.168.1.10 - - [01/Apr/2026:09:16:01] "GET /dashboard" 200 4096
10.0.0.5 - - [01/Apr/2026:09:16:12] "POST /login" 200 512


@Awl1025 ➜ /workspaces/it612/Awk_Participation (main) $ awk '{print $1}' log.txt | sort | uniq -c | sort -nr
      3 10.0.0.5
      2 192.168.1.15
      2 192.168.1.10
      1 192.168.1.20


@Awl1025 ➜ /workspaces/it612/Awk_Participation (main) $ sed 's/\[.*\] //' log.txt
192.168.1.10 - - "GET /index.html" 200 1024
192.168.1.15 - - "GET /api/users" 500 312
10.0.0.5 - - "POST /login" 401 215
192.168.1.10 - - "GET /dashboard" 200 4096
10.0.0.5 - - "POST /login" 401 215
10.0.0.5 - - "POST /login" 200 512
192.168.1.15 - - "GET /api/users" 500 312