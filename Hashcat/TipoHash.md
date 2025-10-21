## MODOS DE HASHCAT ('-m') POR TIPO DE HASH

|   Tipo de Hash    |   Modo ('-m')     | Descripción breve                         |
|-----------------------------------------------------------------------------------|
| MD5               | 0                 | Hash simple                               |
| SHA1              | 100               | Usado en Git, certificados, etc.          |
| SHA256            | 1400              | Hash fuerte, usado en Open SSL y JWT      |
| SHA512            | 1700              | Variante más robusta de SHA               |
| NTLM              | 1000              | Hash de contraseñas en Windows            |
| bcrypt            | 3200              | Hash lento, usado en sistemas modernos    |
| WPA/WPA2          | 22000             | Handshake de redes Wi-Fi                  |
| LM (Lan Manager)  | 3000              | Hash obsoleto                             |
| MySQL 5.x         | 300               | SHA1 doble usado en MySQL                 |
| MD5 + Salt        | 400               | Hash con sal usado en CMS                 |