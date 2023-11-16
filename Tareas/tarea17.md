# Jwt
## Que es? 
_JSON Web Token (JWT) es un estándar abierto ( RFC 7519 ) que define una forma compacta y autónoma de transmitir información de forma segura entre partes como un objeto JSON. Esta información se puede verificar y confiar porque está firmada digitalmente. Los JWT se pueden firmar usando un secreto (con el algoritmo HMAC ) o un par de claves pública/privada usando RSA o ECDSA ._
## ¿Cuándo debería utilizar tokens web JSON?
_A continuación se muestran algunos escenarios en los que los tokens web JSON son útiles: _
* Autorización :
  
    _este es el escenario más común para usar JWT. Una vez que el usuario haya iniciado sesión, cada solicitud posterior incluirá el JWT, lo que permitirá al usuario acceder a rutas, servicios y recursos permitidos con ese token. El inicio de sesión único es una característica que JWT utiliza ampliamente hoy en día, debido a su pequeña sobrecarga y su capacidad para usarse fácilmente en diferentes dominios._

* Intercambio de información :

    _los tokens web JSON son una buena forma de transmitir información de forma segura entre las partes. Dado que los JWT se pueden firmar (por ejemplo, utilizando pares de claves pública/privada), puede estar seguro de que los remitentes son quienes dicen ser. Además, como la firma se calcula utilizando el encabezado y la carga útil, también puedes verificar que el contenido no haya sido manipulado._

## Estructura
_En su forma compacta, los JSON Web Tokens constan de tres partes separadas por puntos ( .), que son:_

* Encabezamiento
* Carga útil
* Firma

### Encabezamiento
_El encabezado normalmente consta de dos partes: el tipo de token, que es JWT, y el algoritmo de firma que se utiliza, como HMAC SHA256 o RSA._
_Luego, este JSON está codificado en Base64Url para formar la primera parte del JWT._
### Carga útil
_La segunda parte del token es la carga útil, que contiene los reclamos. Los reclamos son declaraciones sobre una entidad (normalmente, el usuario) y datos adicionales. Hay tres tipos de reclamaciones: reclamaciones registradas , públicas y privadas ._
#### Reclamaciones registradas 
_son un conjunto de reclamaciones predefinidas que no son obligatorias pero sí recomendadas, para proporcionar un conjunto de reclamaciones útiles e interoperables. Algunos de ellos son: iss (emisor), exp (tiempo de vencimiento), sub (asunto), aud (audiencia) y otros ._
### Reclamaciones públicas
_pueden ser definidas a voluntad por quienes utilizan JWT. Pero para evitar colisiones, deben definirse en el Registro de tokens web JSON de IANA o definirse como un URI que contenga un espacio de nombres resistente a colisiones._

### Reclamos privados.
_estos son reclamos personalizados creados para compartir información entre partes que acuerdan usarla y no sonreclamos registrados ni públicos ._
_Luego, la carga útil se codifica en Base64Url para formar la segunda parte del token web JSON_

## Firma
_Para crear la parte de la firma, debe tomar el encabezado codificado, la carga útil codificada, un secreto, el algoritmo especificado en el encabezado y firmarlo._
_La firma se utiliza para verificar que el mensaje no se modificó en el camino y, en el caso de tokens firmados con una clave privada, también puede verificar que el remitente del JWT es quien dice ser._

## Poniendo todo junto
_El resultado son tres cadenas de URL Base64 separadas por puntos que se pueden pasar fácilmente en entornos HTML y HTTP, a la vez que son más compactas en comparación con estándares basados ​​en XML como SAML._
