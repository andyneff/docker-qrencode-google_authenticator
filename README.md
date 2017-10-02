# Simplest usage: docker-compose

```
docker-compose run --rm qrcode
```

And it will automatically mount your .google_authenticator file into the
container as read-only and print out the QR code associated with it

# Using just docker

```
docker run -it --rm andyneff/docker-qrencode-google_authenticator
```

# Options

- Use a different directory: `-v /root/.google_authenticator:/key/.google_authenticator:ro`
- Can't mount a single file (Windows, etc...): `-v ~:/key:ro`
- Use a custom filename: `-e AUTH_FILE=custom_file`
- Using an otp other than `totp`: `-e OTP_TYPE=totp`
- Adding a custom comment (default is `Replay Code`): `-e COMMENT="Important code"`
- Using an output other than `ANSI`: `-e OUTPUT_FORMAT=UTF8`
    - Valid options are: ANSI,ANSI256,ASCII,ASCIIi,UTF8,ANSIUTF8