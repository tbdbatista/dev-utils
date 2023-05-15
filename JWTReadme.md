# Como usar JWT

## Kotlin

Para usar o JWT em uma aplicação Kotlin, você pode utilizar a biblioteca "Auth0 JWT" disponível no repositório do Maven.

1. Adicione a dependência da biblioteca ao arquivo build.gradle da sua aplicação:

```kotlin
dependencies {
    implementation 'com.auth0:java-jwt:3.18.2'
}
```

2. Importe as classes necessárias no seu código:

```kotlin
import com.auth0.jwt.JWT
import com.auth0.jwt.algorithms.Algorithm
import java.util.*
```

3. Crie um token JWT com as informações do usuário autenticado:

```kotlin
val algorithm = Algorithm.HMAC256("secretpassword") // Defina a chave secreta para a assinatura do token
val issuer = "meuapp.com" // Defina o emissor do token
val subject = "123456" // Defina o assunto do token (geralmente o ID do usuário)
val expiresAt = Date(System.currentTimeMillis() + 3600000) // Defina a data de expiração do token (1 hora a partir do momento atual)
val token = JWT.create()
        .withIssuer(issuer)
        .withSubject(subject)
        .withExpiresAt(expiresAt)
        .sign(algorithm)
```

4. Verifique a validade e autenticidade do token recebido pelo cliente:

```kotlin
val token = "meu_token_jwt" // Receba o token do cliente
try {
    val algorithm = Algorithm.HMAC256("secretpassword") // Defina a mesma chave secreta utilizada na assinatura do token
    val verifier = JWT.require(algorithm)
            .withIssuer("meuapp.com") // Verifique se o emissor do token é válido
            .build()
    val jwt = verifier.verify(token)
    val subject = jwt.subject // Acesse o assunto (ID do usuário) do token
    // Faça o tratamento necessário para a autorização do usuário
} catch (exception: Exception) {
    // Trate o erro caso o token seja inválido ou tenha expirado
}
```

Lembre-se de proteger as informações confidenciais do usuário e utilizar a biblioteca de forma segura e eficiente para garantir a autenticação e autorização seguras da sua aplicação Kotlin.
