# Authorization - Distributed system

- How do we ensure presented permission are valid?
- How do we build a scalable solution?

## OAuth2.0 and OpenId connect

- OAuth2 dose not impose any format for tokens
- OpenId connect states the Id token is in the JWT format
  JWT:
- Header (Json) [required]
  - alg: the main algorithm in use for signing and or decrypting the JWT
  - typ: the media type of the JWT
  - cty: this is the content type ordinary this omitted
- Payload (Json) [required]
  - iss: This id a case sensitive string or URL which uniquely indentifies the party that issused the JWT.
  - sub A case sensitive string or URI that uniquely indentifies the party to which the JWT relates.
  - aud: A case sensitive string or URI or array of such data wich defines the audience which the JWT is suitable for.
  - exp: expiration date and time represented using the POSIX format or seconds by a POSIX value.
  - nbf: A number representing the time where the JTW is not before.
    iat: This is the issued at time which is a POSIX value for the date and time of issue.
  - jti:
- Signature [optional]

- JWT Public claims:
  - Registered by IANA JSON Web Token Claims registry
  - Can be custom as long as collision resistant
    {
    profile: "",
    name: "full name"
    email: "email.address@abc.xyz"
    }
- JWT Private claims:

  - Defined by consumers and producers of the JWT
  - Adhoc claims and can be any value encoded to JSON
    {
    "basket.update": true,
    "profile.modify": true,
    "catalog.service": ["read", "write", "delete"]
    }

- JWT - Unsecured
- JWT - Web signatures (System can validate and just the token)

JWT - alg: none attack
JWT -RS256 Public Key as HS256 secret Attack
