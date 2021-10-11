# 
1. user tollll https://github.com/internetwache/GitTools
2. ![image](https://user-images.githubusercontent.com/65381453/136646924-cfcc29ef-f6be-4ce6-9012-a6dff8278193.png)

firse 
cat logs/refs/heads/master

![image](https://user-images.githubusercontent.com/65381453/136646941-de394707-7be5-4a4a-b120-8c52f84c4a86.png)

```
2756250c7cd2188bdf8c4cdeddc92bcbe13f1755
```
```
git cat-file -t 2756250c7cd2188bdf8c4cdeddc92bcbe13f1755

```
![image](https://user-images.githubusercontent.com/65381453/136646953-4004ead8-c42a-41d7-9707-fa9b25f21106.png)
```
git cat-file -p 2756250c7cd2188bdf8c4cdeddc92bcbe13f1755

>> tree c2c1d8bde15fa2174d6acd1284d7251579b8a1b4
```
![image](https://user-images.githubusercontent.com/65381453/136646970-c8149b3c-7376-4b06-ac68-7b40e715ddb3.png)

```
git cat-file -p c2c1d8bde15fa2174d6acd1284d7251579b8a1b4
```
![image](https://user-images.githubusercontent.com/65381453/136646981-52035ca0-ac3a-4d61-a965-586f1e449d18.png)

nexxt  git cat-file -p 0d4096f89f4ea65a44c2a4038b6f931c95c5eba4

![image](https://user-images.githubusercontent.com/65381453/136768986-d12c6e7d-6546-4799-afff-bc8d8efbd5d4.png)

i get file index.php

```
<?php

/**
 * Simple sodium crypto class for PHP >= 7.2
 * @author MRK
 */
class crypto {

    /**
     *
     * @return type
     */
    static public function create_encryption_key() {
        return base64_encode(sodium_crypto_secretbox_keygen());
    }

    /**
     * Encrypt a message
     *
     * @param string $message - message to encrypt
     * @param string $key - encryption key created using create_encryption_key()
     * @return string
     */
    static function encrypt($message, $key) {
        $key_decoded = base64_decode($key);
        $nonce = random_bytes(
                SODIUM_CRYPTO_SECRETBOX_NONCEBYTES
        );

        $cipher = base64_encode(
                $nonce .
                sodium_crypto_secretbox(
                        $message, $nonce, $key_decoded
                )
        );
        sodium_memzero($message);
        sodium_memzero($key_decoded);
        return $cipher;
    }

    /**
     * Decrypt a message
     * @param string $encrypted - message encrypted with safeEncrypt()
     * @param string $key - key used for encryption
     * @return string
     */
    static function decrypt($encrypted, $key) {
        $decoded = base64_decode($encrypted);
        $key_decoded = base64_decode($key);
        if ($decoded === false) {
            throw new Exception('Decryption error : the encoding failed');
        }
        if (mb_strlen($decoded, '8bit') < (SODIUM_CRYPTO_SECRETBOX_NONCEBYTES + SODIUM_CRYPTO_SECRETBOX_MACBYTES)) {
            throw new Exception('Decryption error : the message was truncated');
        }
        $nonce = mb_substr($decoded, 0, SODIUM_CRYPTO_SECRETBOX_NONCEBYTES, '8bit');
        $ciphertext = mb_substr($decoded, SODIUM_CRYPTO_SECRETBOX_NONCEBYTES, null, '8bit');

        $plain = sodium_crypto_secretbox_open(
                $ciphertext, $nonce, $key_decoded
        );
        if ($plain === false) {
            throw new Exception('Decryption error : the message was tampered with in transit');
        }
        sodium_memzero($ciphertext);
        sodium_memzero($key_decoded);
        return $plain;
    }

}

$privatekey = "mRHpcEckKATdwDC/CwpRinDTiAYrn9lzWpTo277omKs=";

$flag = file_get_contents('../flag.txt');

$enc = crypto::encrypt($flag, $privatekey);

echo $enc;

?>

<html>
    <br>
    Only if you could see the source code.
</html>
```

i see 2 func encrypt and decrypt, i change something 

```
$mess  = "fZ1FzNJ4L1cA7/Ynmh7Beu6PBxUNbfdkBpBpysuZDyrWcwqLhB5WYbXkXtNxOBzfKWquG3pj2x0cggORrPJcZvoWXY6mxbu42yl7Hn2/";

$abc = crypto::decrypt($mess, $privatekey);

echo $abc;
```

and run

![image](https://user-images.githubusercontent.com/65381453/136769433-944cb12a-bf1f-4286-861e-d848654b24ca.png)

get flag
