Once your server is configured to receive events, it will listen for any message sent to the endpoint
you configured. For security reasons, you probably want to limit requests to those coming from Shotl. 
The far easiest method is to validate our request trough the signature.

## Headers
All events are sent with two important headers

| Name | Description |
| ----| ------------ |
| X-Date | UNIX timestamp when the event was triggered |
| X-Signature | Sha256 Signature |

## Signature validation
You can compute a hash using your [API password](/getting-started/authentication), and ensure that the hash from
the request matches. Shotl uses an HMAC Sha256 hexdigest **from the body** to compute the hash.

!!! Example
    === "GO"
        ```go
        package main
        
        import (
            "crypto/hmac"
            "crypto/sha256"
            "encoding/base64"
            "fmt"
        )
        
        func ComputeHmac256(message string, secret string) string {
            key := []byte(secret)
            h := hmac.New(sha256.New, key)
            h.Write([]byte(message))
            return base64.StdEncoding.EncodeToString(h.Sum(nil))
        }
        
        func main() {
            body := myFunctionToReadRequestBody()
            fmt.Println(ComputeHmac256(body, "<YOUR API PASSWORD>"))
        }
        ```
    === "PHP"
        ```php
        body = myFunctionToReadRequestBody()
        $s = hash_hmac('sha256', body, '<YOUR API PASSWORD>', true);
        echo base64_encode($s);
        ```
    === "JAVA"
        Dependent on (Apache Commons Codec)[https://commons.apache.org/proper/commons-codec/] to encode in base64.
        ```java
        import javax.crypto.Mac;
        import javax.crypto.spec.SecretKeySpec;
        import org.apache.commons.codec.binary.Base64;
        
        public class ApiSecurityExample {
            public static void main(String[] args) {
                try {
                    String secret = <YOUR API PASSWORD>;
                    String message = myFunctionToReadRequestBody();
                    
                    Mac sha256_HMAC = Mac.getInstance("HmacSHA256");
                    SecretKeySpec secret_key = new SecretKeySpec(secret.getBytes(), "HmacSHA256");
                    sha256_HMAC.init(secret_key);
                    
                    String hash = Base64.encodeBase64String(sha256_HMAC.doFinal(message.getBytes()));
                    System.out.println(hash);
                }
                    catch (Exception e){
                    System.out.println("Error");
                }
            }
        }
        ```        
    