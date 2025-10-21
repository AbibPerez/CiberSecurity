
## Cifrado & Hashing
| Comando                           | Descripción                                                                   | 
|-----------------------------------|-------------------------------------------------------------------------------|
| enc                               | -> Cifrado y descifrado de archivos con algoritmos simétricos (<AES, DES>)    |
| dgst                              | -> Calcular y verifica hashes (<MD5, SHA1, SHA256>)                           |
| rand                              | -> Genera números aleatorios seguros                                          |
| ciphers                           | -> Lista de los cifrados disponibles en OpenSSL                               |
| passwd                            | -> Genera contraseñas encriptadas                                             |

## Llaves & Parámetros   
| Comando                           | Descripción                                                                   |                                          
|-----------------------------------|-------------------------------------------------------------------------------|
| genrsa                            | -> Genera llaves privadas <RSA>                                               |
| rsa                               | -> Procesa llaves <RSA> (convertir formatos, extraer pública)                 |
| rsautl                            | -> Opera con <RSA> (cifrar, descifrar, firmar, verificar)                     |
| dsa                               | -> Procesa llaves <DSA>                                                       |
| gendsa                            | -> Genera llaves privadas <DSA>                                               |
| dsaparam                          | -> Procesa llaves de curva elíptica                                           |
| genpkey                           | -> Genera parámetros para curvas elípticas                                    |
| pkey                              | -> Procesa llaves provadas y públicas                                         |
| pkeyparam                         | -> Muestra parámetros de una llave                                            |
| pkeyutl                           | -> Operaciones con llaves (cifrar, descifrar, firmar, verificar)              |
| dhparam                           | -> Genera parámetros <Diffie-Hellman>                                         |
| gendh                             | -> Genera llaves privadas <DH>                                                |
| prime                             | -> Prueba si un número es primo                                               |

## Certificados & PKI
| Comando                           | Descripción                                                                   |                                          
|-----------------------------------|-------------------------------------------------------------------------------|
| req                               | -> Crea y procesa solicitudes de certificados (CSR)                           |
| x509                              | -> Procesa certificados <X.509>                                               |
| verify                            | -> Verifica certificados                                                      |
| ca                                | -> Herramienta de Certificate Authority (firma de certificados)               |
| crl                               | -> Procesa listas de revocación de certificados (CRL)                         |
| cr12pkcs7                         | -> Convierte CRL a <PKCS#7>                                                   |
| pkcs7                             | -> Procesa estructuras <PKCS#7>                                               |
| pkcs8                             | -> Convierte llaves privadas al formato <PKCS#8>                              |
| pkcs12                            | -> Procesa archivos <PKCS#12> (.p12/.pfx con certificados y llaves)           |
| cms                               | -> Procesa mensajes <CMS> (Cryptographic Message Syntax)                      |
| smime                             | -> Firma, encripta y procesa mensajes <S/MIME>                                |
| spkac                             | -> Procesa SPKAC (usado en generación de certificados por navegadores)        |
| ocsp                              | -> Hace consultas <OCSP> para validar certificados en línea                   |
| ts                                | -> Procesa <timestamping> (sellado de tiempo digital)                         |
| nseq                              | -> convierte entre <ASN.1> y secuencias numeradas                             |
| asn1parse                         | -> Analiza y muestra estructuras <ASN.1>                                      |

## Conexiones & Debugging
| Comando                           | Descripción                                                                   |                                          
|-----------------------------------|-------------------------------------------------------------------------------|
| s_client                          | -> Cliente SSL/TLS para probar conexiones seguras                             |            
| s_server                          | -> Servidor SSL/TLS para pruebas                                              |
| s_time                            | -> Mide el rendimiento de conexiones SSL/TLS                                  |      
| sess_id                           | -> Muestra y manipula sesiones SSL                                            | 
| engine                            | -> Lista y administra motores criptográficos de OpenSSL                       |                 
| errstr                            | -> Muestra el texto de un código de error de OpenSSL                          |              
| speed                             | -> Prueba el rendimiento de algoritmos criptográficos                         |               
| version                           | -> Muestra la versión de OpenSSL                                              |

## Message Digest (Hash)
| Comando                           | Descripción                                                                   |
|-----------------------------------|-------------------------------------------------------------------------------|
| dgst                              | -> Calcula y verifica resúmenes criptográficos                                |
| Sintaxis                          | [openssl][dgst] [-algoritmo][archivo.txt]                                     |
#### Algoritmos disponibles
| Algoritmo                         | Descripción                                                                   |
|-----------------------------------|-------------------------------------------------------------------------------|
| md2                               | -> Hash MD2 (obsoleto, inseguro)                                              |
| md4                               | -> Hash MD4 (obsoleto, inseguro)                                              |
| md5                               | -> Hash MD5 (Inseguro para firmas)                                            |            
| rmd160                            | -> RIPEMD-160 (alternativa a SHA-1)                                           |             
| sha                               | -> SHA genérico                                                               |
| sha1                              | -> SHA-1                                                                      |


## Ciphers
| Comando                           | Descripción                                                                   |
|-----------------------------------|-------------------------------------------------------------------------------|
# Prefijo ==> openssl enc -...
enc                                 -> Cifrado y descifrado de archivos con algoritmos simétricos
*AES —— CBC*
> Sintaxis ->> [openssl][enc] [-aes-128/192/256-cbc] [-in][archivo.txt] [-out][archivo.enc] [-k][contraseña]
-aes-128-cbc                        -> AES de 128 bits en modo CBC
-aes-192-cbc                        -> AES de 192 bits en modo CBC
-aes-256-cbc                        -> AES de 256 bits en modo CBC
*AES —— ECB*
> Sintaxis ->> [openssl][enc] [-aes-128/192/256-ecb] [-in][archivo.txt] [-out][archivo.enc] [-k][contraseña]
-aes-128-ecb                        -> AES de 128 bits en modo ECB
-aes-192-ecb                        -> AES de 192 bits en modo ECB
-aes-256-ecb                        -> AES de 256 bits en modo ECB
*Camellia —— CBC*
-camellia-128-cbc                   -> Camellia de 128 bits en modo CBC
-camellia-192-cbc                   -> Camellia de 192 bits en modo CBC
-camellia-256-cbc                   -> Camellia de 256 bits en modo CBC
*Camellia —— ECB*
-camellia-128-ecb                   -> Camellia de 128 bits en modo ECB
-camellia-192-ecb                   -> Camellia de 192 bits en modo ECB
-camellia-256-ecb                   -> Camellia de 256 bits en modo ECB
*Blowfish(BF)*
-bf                                 -> Blowfish en modo CBC (by default)
-bf-cbc                             -> Blowfish en modo CBC (Cipher Block Chaining)
-bf-cfb                             -> Blowfish en modo CFB (Cipher Feedback)
-bf-ecb                             -> Blowfish en modo ECB (Electronic Codebook)
-bf-ofb                             -> Blowfish en modo OFB (Output Feedback)
*DES*
-des-cbc/cfb/ecb/ofb                -> DES clásico
-des-ede-cbc/cfb/ecb/ofb            -> Double DES
-des-ede3-cbc/cfb/ecb/ofb           -> Triple DES
-desx                               -> Variante de DES con XOR extendido
*IDEA*
-idea-cbc/cfb/ecb/ofb               -> Usado en PGP anteriormente
*RC2 (Rivest Ciphers)*
-rc2                                -> RC2 en modo CBC (by default)
-rc2-40-cbc                         -> RC2 en CBC con clave de 40 bits
-rc2-64-cbc                         -> RC2 en CBC con clave de 64 bits
-rc2-cbc                            -> RC2 en CBC, requiere IV
-rc2-cfb                            -> RC2 en CFB (flujo)
-rc2-ecb                            -> RC2 en ECB (repite patrones => Inseguro)
-rc2-ofb                            -> RC2 en OFB (flujo), requiere IV
*RC4*
-rc4                                -> RC4 genérico (flujo de bytes)
-rc4-40                             -> RC4 con clave de 40 bits
*RC5*
-rc5                                -> RC5 genérico
-rc5-cbc                            -> RC5 en CBC
-rc5-cfb                            -> RC5 en CFB
-rc5-ecb                            -> RC5 en ECB
-rc5-ofb                            -> RC5 en OFB
*SEED*
-seed                               -> SEED en CBC (by default)
-seed-cbc                           -> SEED en CBC (seguro usando IV aleatorio)
-seed-cfb                           -> SEED en CFB
-seed-ecb                           -> SEED en ECB
-seed-ofb                           -> SEED en OFB
*CAST*
-cast                               -> CAST5 en modo CBC (by default)
-cast-cbc                           -> CAST5 en CBC (IV aleatorio)
-cast5-cfb                          -> CAST5 en CFB
-cast5-ecb                          -> CAST5 en ECB
-cast5-ofb                          -> CAST5 en OFB