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
### Valid Response 

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

## Upload Files via Application Dashboard

1. Create an account and log in at https://pinata.cloud.

2. Now, go to https://app.pinata.cloud/pinmanager, click the "+ Add" button at the top right, and upload your file.

>
![image](https://github.com/user-attachments/assets/9add7ffa-ae1f-4d1a-8b73-986c89a48757)

3. After the file upload, copy the CID and use it with your target.

>
![image](https://github.com/user-attachments/assets/5d9bf95b-a055-403d-a9b2-11cdf104edc6)

### Examples

_XSS via SVG_
https://ipfs.io/ipfs/QmRhLTFfE8tyNWvN1sX1gfJnhmn8dRwUJ17whge6wouhCF

_XSS via html/js_
https://ipfs.io/ipfs/QmWZLybRPA12UwkYbJdjZjE82exfPoSmpCaVyRC7EnPrNP

_Note: With the free plan, there are some restrictions, such as limitations on uploading HTML and JS files._

