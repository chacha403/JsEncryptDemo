1. generate private key:

   openssl genrsa -out rsa_2048_priv.pem 2048

2. generate public key (used by h5):

   openssl rsa -pubout -in rsa_2048_priv.pem -out rsa_2048_pub.pem


3. save private key using PKCS#8 format

   openssl pkcs8 -topk8 -nocrypt -in  rsa_2048_priv.pem -out rsa_2048_priv.p8

   edit the ouput file "rsa_2048_priv.p8", remove first & last line, concatenate the left lines and save to db as private key
