### HTTP Request (upload)

```
POST /pinning/pinFileToIPFS HTTP/1.1
Host: api.pinata.cloud
Pinata_api_key: <your_api_key>
Pinata_secret_api_key: <your_secret_api_key>
Accept: */*
Content-Type: multipart/form-data; boundary=------------------------d74496d66958873e
Content-Length: 258

--------------------------d74496d66958873e
Content-Disposition: form-data; name="file"; filename="bc_poc.txt"
Content-Type: text/plain

Uploded By Bugcrowd Researcher
--------------------------d74496d66958873e--
```
## Using curl (upload)

```
curl -X POST "https://api.pinata.cloud/pinning/pinFileToIPFS" \
     -H "pinata_api_key: <your_api_key>" \
     -H "pinata_secret_api_key: <your_secret_api_key>" \
     -F file=@/home/user/poc.txt
```
### Vaild Response 

```
{
  IpfsHash: "****",
  ..
}
```
## Retrieve File

```
curl "https://${GATEWAY}/ipfs/${CID}"
```

> {CID} = $IpfsHash

> {GATEWAY} = Search for `.mypinata.cloud` in same endpoint response.


