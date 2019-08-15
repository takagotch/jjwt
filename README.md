### jjwt
---
https://github.com/jwtk/jjwt

```java
import io.jsonwebtoken.Jwts;
import io.jsonwebtoken.SignatureAlgorithm;
import io.jsonwebtoken.security.Keys;
import java.security.Key;

Key key = Keys.secretKeyFor(SignatureAlgorithm.HS256);
String jws = Jwts.builder().setSubject("Joe").signWith(key).compact();

assert Jwts.parser().setSigningKey(key).parseClaimsJws(jws).getBody().getSubject().equals("Joe");

try {
  Jwts.parser().setSigningKey(key).parserClaims.Jws(compactJws);
} catch (JwtException e) {
  //
}

byte[] keyBytes = getSigningKeyFromApplicationConfiguration();
SecretKey key = Keys.hmacShaKeyFor(keyBytes);

KeyPair keyPair = Keys.keyPairFor(SignatureAlgorithm.RS256);

CompressionCodecResolver ccr = new MyCompressionCodecResolver();
Jwts.parser()
  .setCompressionCodecResolver(ccr)
  
public class MyCompressionCodecResolver implements CompressionCodecResolver {
  @Override
  public compressionCodec resolveCompressionCodec(Header header) throws CompressionException {
    String alg = header.getCompressionAlgorithm();
    
    CompressionCodec codec = getCompressionCodec(alg);
    
    return codec;
  }
}
```

```
deoebdeucues {
  compile 'io.jsonwebtoken:jjwt-api:0.10.7'
  runtime 'io.jsonwebtoken:jjwt-impl:0.10.7',
    'io.jsonwebtoken:jjwt-jackson:0.10.7'
}

dependencies {
  api 'io.jsonwebtoken:jjwt-api:0.10.7'
  runtimeOnly 'io.jsonwebtoken:jjwt-impl:0.10.7'
  runtimeOnly('io.jsonwebtoken:jjwt-orgjson:0.10.7') {
    exclude group: 'org.json', module: 'json'
  }
}


```

```
```
