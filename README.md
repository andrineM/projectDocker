# projectDocker

Add a custom configuration to Nginx


  # Enable TLS and HTTP2
  listen     443 ssl http2;

  # Use only TLS
  ssl_protocols TLSv1 TLSv1.1 TLSv1.2;  # Tell client which ciphers are available
  ssl_prefer_server_ciphers on;
  ssl_ciphers ECDH+AESGCM:ECDH+AES256:ECDH+AES128:DH+3DES:!ADH:!AECDH:!MD5;  # Use our own DH params
  ssl_dhparam /etc/nginx/certs/dhparam.pem;  # Enable OCSP stapling
  ssl_stapling on;
  ssl_stapling_verify on;
  ssl_trusted_certificate /etc/ssl/lets-encrypt-x3-cross-signed.pem;  # Enable HSTS
  add_header Strict-Transport-Security "max-age=31536000" always;  # Optimize session cache
  ssl_session_cache   shared:SSL:40m;
  ssl_session_timeout 4h;  # Enable session tickets
  ssl_session_tickets on; 
  
  

