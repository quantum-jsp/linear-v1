---
title: "Authentication"
slug: "authentication-validation-1"
excerpt: ""
hidden: false
metadata: 
  image: []
  robots: "index"
createdAt: "Sat Jul 27 2019 22:05:38 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Fri Apr 30 2021 14:55:08 GMT+0000 (Coordinated Universal Time)"
---
To access the Linear API you will need either a certificate or an API Key.  Which one to use will be dependent on the access granted and resources called. For partners looking to simply submit applications (using the **Prefill App** or **Submit App** endpoint), you can use a certificate or API Key.  We find the majority of partners using just an API Key in these instances.  This will be provided to you by Linear and allows you to submit applications directly to our server from your website.  For all other uses of the API (any line of credit functionality or calls to get customer information), we require certificate authentication.  Additional information on client certificates can be found below.

> 📘 General Note Regarding Authentication
> 
> If you are using resources to both submit applications and get subsequent customer information (or access line of credit functionality), we recommend using certificate authentication for all calls.

# Securing API Endpoints Using Client Certificates

A client certificate-based authentication scheme is a robust way of authenticating our partners. Even if a certificate is compromised, without the private key there is no way to misuse it. For APIs that expose customer information, Linear requires a certificate mechanism which is much safer than a password-based mechanism. In this handshake scheme, the request coming to Linear's API endpoint needs to be signed by the client certificate from our partner. 

## Step 1: Creating a Certificate Authority (CA) Cert

The first step in this process, assuming you do not already have one, is to generate a root certificate on which you will base your client certificate request. Ideally, you would like to have this certificate from a trusted Certificate Authority like VeriSign, GeoTrust or Entrust, but a self-signed certificate is sufficient for this purpose.  Once created, you'll need to add this to your Trusted Root CA in the machine where the API call will occur from, as this will become your root certificate for the client certificate request.

Provided below is an example command of a self-signed root certificate with OpenSSL (which works for Linux, Windows, Mac and Android and can be downloaded **[here](https://wiki.openssl.org/index.php/Binaries)**).

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout privateKey.key -out certificate.crt
```

## Step 2: Client Certificate Signing Request (CSR)

After creating a CA Cert, you'll need to create the client certificate request using the CA Cert  (certificate.crt) created in Step 1.  An example of the command for this client certificate request is provided below:

```
openssl x509 -x509storeq -in certificate.crt -out CSR.csr -signkey privateKey.key
```

This command will create both a private and a public key.  The private key should not be shared and kept secure and safe. The .csr file (CSR.csr) from the command above should be sent to Linear. 

## Step 3: Packaging the Certificate

Linear will return a signed certificate along with our root certificate, which will need to be installed on your server(s) being used to make the API calls.  Installing the root and signed certificate to your target environment is best done by packaging them.  The packaged file will be in PFX file (or other applicable file type), for which we have provided an example command below:

```
openssl pkcs12 -export -out certificate.pfx -inkey privateKey.key -in certificate.crt -certfile FundationRootCertificate.cr*t
```

Once the packaged file is created, you can import this into the certificate store using the following command on a Windows machine

```
CERTUTIL -f -importpfx “certificate.pfx"
```

Once complete, you can now include your packaged certificate and call our API.  Below is an example using the previously generated PFX file and Postman to call our API.

<br/>
![Postman] (https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
