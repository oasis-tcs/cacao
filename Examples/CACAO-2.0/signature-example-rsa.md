# Playbook Signature Using RSA

## Key Information

### Step 0: Given the following public and private keys

```
-----BEGIN PRIVATE KEY-----
MIIEvAIBADANBgkqhkiG9w0BAQEFAASCBKYwggSiAgEAAoIBAQCm0pnIU9K2+Y6VvRaKE4GGUdSv
rAUMcL61buEkC519NDmYdlCkHw+gzPTu51kD50bx2FQg+SZeWnVOBER5hMd2HGG5/TL8aFulm/kk
9gfHfBq074dY7apiSNEwRytaE8x1pWRL9d7+WJoxyjDiNihZoWbxWht5izJUPZtZZ3KXiOhMQROb
VnjtGed9HXmRWFW51WsPMQWYziddX/p2YiDXzhEkTiG23AEXFHypkJALBOImayjInF9RHQazh48p
zmwHQ1OSYVlzmSVBKK13rtEmfaV2FuoTsSkOXheUi35TIsmbWC4IGW2JrwCCR7t1e6GkHuFDosnB
jgSPO2GQnwg/AgMBAAECggEAKT6KTNAEmb5rdTPxvaOC832J0wD5opDBZcQLH8lLX6go0Tv3Rgxz
5bKmn+ZMyL1GegadDiXrSYqd0/MUJuMgGWB8/OnP0D3Q4soEOBIn7DcPt0o9MUxZQsF0DraZzkR0
2WVRvcIFJucrAEJYAaWYJkjUVbmMb2ltwQwWO21rFHGbpE73nsfr/oAWsZEvKsQZoYm4fh5jVI5+
wKyRnKaN1uqAcNgj75cdywCHBVwgEefEgOPM77CDMH0+JumSirQiBfR35+HWRwHwpm09wI6Aqtvg
y5bzxvLDDRgrhX4LCPtUHGrUXNJHRKYiHQX6P6bIVuBrHV6VFpyS+5weu0w6kQKBgQDQo4QeLtO7
S3KH8UL3lX4lhH1K7/Q99uBHmvLXdiDkHjLbBbh0JfrHgHtnK9bvJ2GvVcwhI9fTiO1p1o5RM5jb
iVUSCS91sLcTPFv8X83sExBZnrvlSlb/va+4yW+Lzvr6ZiDlZYsVRNvNAHUTojHRCOH2P4eX1+ql
5P4FMdfvSQKBgQDMsQ4LBpxjD9KdDzJzw9a0xbL47QdCeZBqNUy6MvwLE0+KsF+prvoigNZCaTcJ
2FfoPxpE3/o0A/byCTuDkfddrd/hcAO0gd1R9CYJDXJfnIbZfheUmHW7ShbXyqhpqQKVjzH+jnLq
VjbGD6tz3dN+AwNgULD/vvwXM2TWpu9TRwKBgGkPPdMZD2NLzaNouKkFbR0lRxY6GEovi6Zi/w/C
GzPjhQZHLifGjC5zozBDohqRQR5SXNT/QInzdGGMOePn0HwT/nNzjqN71eRoy4UdFQtgWiZWyRTf
x0lGUjsBrBrBoh3+2WfKJywRnYDwTwQQ83boOyiNuxCaGD1rPwKMo8iJAoGAPIePE4uc615edbts
u/cJouNjjWDqaKnyHrYsPlOdXNkVCHonj9ICffmDYpgignLLbA5dAkkJgCA8Ak7gnoOnlrg4ID4z
mklc3UNJjBvB2qw65E35QyPijMPYBXAUZUppTTjPG+ub59ge0msH1Hegdv8FHJJABSDBA0tbYm5z
DzkCgYA9/0KtWKFMhF3v01L54AXF5b15RroBhZAfzI1U0wPO4J6Tz+1KqmtrwHTBPI36nzITIhlM
hcoTsMRMgnv0NHzxlcQQmAy3foFBFOyHXql3hPtWbEViB5jQs4cP5ts1oivVhrEtrrE51TG4V/Ef
fD1JKiHl7MECYEMyBz31PsRCuw==
-----END PRIVATE KEY-----
```

```
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+
tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3wa
tO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47Rnn
fR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NT
kmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4Ejzth
kJ8IPwIDAQAB
-----END PUBLIC KEY-----
```

## Signing a Playbook

### Step 1: Create or parse a JSON playbook object to sign

```json
{
  "type": "playbook",
  "spec_version": "cacao-2.0",
  "id": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
  "name": "Playbook 1",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created": "2022-05-18T11:31:31.319Z",
  "modified": "2022-05-18T11:31:31.319Z",
  "signatures": [
    {
      "type": "jss",
      "id": "jss--af4b4bf3-677a-411d-887a-1f6fa5090c05",
      "created_by": "identity--be59c641-b2d5-4930-94fc-6fd583524fc6",
      "created": "2023-02-02T14:31:31.319Z",
      "modified": "2023-02-02T14:31:31.319Z",
      "signee": "Existing Example Company",
      "valid_from": "2023-02-02T14:31:31.319Z",
      "valid_until": "2023-06-18T11:31:31.319Z",
      "related_to": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
      "related_version": "2022-05-18T11:31:31.319Z",
      "hash_algorithm": "sha-256",
      "algorithm": "RS256",
      "public_key": "some public key",
      "value": "some signature"
    }
  ]
}
```

### Step 2: Temporarily remove any existing signature objects contained in the playbook's signatures property

```json
{
  "type": "playbook",
  "spec_version": "cacao-2.0",
  "id": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
  "name": "Playbook 1",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created": "2022-05-18T11:31:31.319Z",
  "modified": "2022-05-18T11:31:31.319Z"
}
```

### Step 3:  Create and add signature to playbook

```json
{
  "type": "playbook",
  "spec_version": "cacao-2.0",
  "id": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
  "name": "Playbook 1",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created": "2022-05-18T11:31:31.319Z",
  "modified": "2022-05-18T11:31:31.319Z",
  "signatures": [
    {
      "type": "jss",
      "id": "jss--af892292-c4b4-47eb-9be6-4897ff4b9388",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2023-01-10T17:39:31.319Z",
      "modified": "2023-01-10T17:39:31.319Z",
      "signee": "ACME Cyber Company",
      "valid_from": "2023-01-10T17:39:31.319Z",
      "valid_until": "2023-06-10T17:39:31.319Z",
      "related_to": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
      "related_version": "2022-05-18T11:31:31.319Z",
      "hash_algorithm": "sha-256",
      "algorithm": "RS256",
      "public_key": "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3watO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47RnnfR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NTkmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4EjzthkJ8IPwIDAQAB"
    }
  ]
}
```

### Step 4: Create a JCS [RFC8785] canonical version of the playbook from step 3

```json
{"created":"2022-05-18T11:31:31.319Z","created_by":"identity--5abe695c-7bd5-4c31-8824-2528696cdbf1","id":"playbook--a0777575-5c4c-4710-9f01-15776103837f","modified":"2022-05-18T11:31:31.319Z","name":"Playbook 1","signatures":[{"algorithm":"RS256","created":"2023-01-10T17:39:31.319Z","created_by":"identity--5abe695c-7bd5-4c31-8824-2528696cdbf1","hash_algorithm":"sha-256","id":"jss--af892292-c4b4-47eb-9be6-4897ff4b9388","modified":"2023-01-10T17:39:31.319Z","public_key":"MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3watO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47RnnfR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NTkmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4EjzthkJ8IPwIDAQAB","related_to":"playbook--a0777575-5c4c-4710-9f01-15776103837f","related_version":"2022-05-18T11:31:31.319Z","signee":"ACME Cyber Company","type":"jss","valid_from":"2023-01-10T17:39:31.319Z","valid_until":"2023-06-10T17:39:31.319Z"}],"spec_version":"cacao-2.0","type":"playbook"}
```

### Step 5: Create a hash (SHA256 in hex) of the canonical version of playbook from step 4

```
973bb6492184e4681b1eab9df1f56926fc1a91582e3529bfd0bfb231e1c51b0a
```

### Step 6: Sign the hash from step 5 using the algorithm defined in the signature object and base64URL.encode it (RS256)

Signature:  

```
gXyPW--uUKvGXRh_oDC7IYlx13hGmkiQw6XX3YX_V_i4Y39OPilf0q0qf46aO3IrvG-5_fgeQ3dIunmizYneaVJKjsXo-gkJczvGDehlTjS7MBUIGyD9DRd41DnaxWWwzU-T4sZCur664_3J0C-WRCDgZxiB_ItFpeSnPJ8rR8GRFO6M9YS-ejEGJl-sd_hfZUqjZOE_S_UWp_Fd9QYlP2cWDvGH8vFhx2ek9KovEob5Bh2LX_Gaf7t237B34wKeN4B8aqapyTh3Q8v_Z61bDTNLyi6ZA8zcrUOgCVLVMx_EFizx31WIDZrePsSpX4bfRurcvRyvNNVdWLaS96JYog
```

### Step 7:  Add the new digital signature from step 6 to the signature value property (with existing signatures, if any)

```json
{
  "type": "playbook",
  "spec_version": "cacao-2.0",
  "id": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
  "name": "Playbook 1",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created": "2022-05-18T11:31:31.319Z",
  "modified": "2022-05-18T11:31:31.319Z",
  "signatures": [
    {
      "type": "jss",
      "id": "jss--af4b4bf3-677a-411d-887a-1f6fa5090c05",
      "created_by": "identity--be59c641-b2d5-4930-94fc-6fd583524fc6",
      "created": "2023-02-02T14:31:31.319Z",
      "modified": "2023-02-02T14:31:31.319Z",
      "signee": "Existing Example Company",
      "valid_from": "2023-02-02T14:31:31.319Z",
      "valid_until": "2023-06-18T11:31:31.319Z",
      "related_to": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
      "related_version": "2022-05-18T11:31:31.319Z",
      "hash_algorithm": "sha-256",
      "algorithm": "RS256",
      "public_key": "some public key",
      "value": "some signature"
    },
    {
      "type": "jss",
      "id": "jss--af892292-c4b4-47eb-9be6-4897ff4b9388",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2023-01-10T17:39:31.319Z",
      "modified": "2023-01-10T17:39:31.319Z",
      "signee": "ACME Cyber Company",
      "valid_from": "2023-01-10T17:39:31.319Z",
      "valid_until": "2023-06-10T17:39:31.319Z",
      "related_to": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
      "related_version": "2022-05-18T11:31:31.319Z",
      "hash_algorithm": "sha-256",
      "algorithm": "RS256",
      "public_key": "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3watO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47RnnfR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NTkmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4EjzthkJ8IPwIDAQAB",
      "value": "gXyPW--uUKvGXRh_oDC7IYlx13hGmkiQw6XX3YX_V_i4Y39OPilf0q0qf46aO3IrvG-5_fgeQ3dIunmizYneaVJKjsXo-gkJczvGDehlTjS7MBUIGyD9DRd41DnaxWWwzU-T4sZCur664_3J0C-WRCDgZxiB_ItFpeSnPJ8rR8GRFO6M9YS-ejEGJl-sd_hfZUqjZOE_S_UWp_Fd9QYlP2cWDvGH8vFhx2ek9KovEob5Bh2LX_Gaf7t237B34wKeN4B8aqapyTh3Q8v_Z61bDTNLyi6ZA8zcrUOgCVLVMx_EFizx31WIDZrePsSpX4bfRurcvRyvNNVdWLaS96JYog"
    }
  ]
}
```

## Verifying a Playbook

### Step 1: Receive and parse the JSON playbook object to verify

```json
{
  "type": "playbook",
  "spec_version": "cacao-2.0",
  "id": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
  "name": "Playbook 1",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created": "2022-05-18T11:31:31.319Z",
  "modified": "2022-05-18T11:31:31.319Z",
  "signatures": [
    {
      "type": "jss",
      "id": "jss--af892292-c4b4-47eb-9be6-4897ff4b9388",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2023-01-10T17:39:31.319Z",
      "modified": "2023-01-10T17:39:31.319Z",
      "signee": "ACME Cyber Company",
      "valid_from": "2023-01-10T17:39:31.319Z",
      "valid_until": "2023-06-10T17:39:31.319Z",
      "related_to": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
      "related_version": "2022-05-18T11:31:31.319Z",
      "hash_algorithm": "sha-256",
      "algorithm": "RS256",
      "public_key": "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3watO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47RnnfR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NTkmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4EjzthkJ8IPwIDAQAB",
      "value": "gXyPW--uUKvGXRh_oDC7IYlx13hGmkiQw6XX3YX_V_i4Y39OPilf0q0qf46aO3IrvG-5_fgeQ3dIunmizYneaVJKjsXo-gkJczvGDehlTjS7MBUIGyD9DRd41DnaxWWwzU-T4sZCur664_3J0C-WRCDgZxiB_ItFpeSnPJ8rR8GRFO6M9YS-ejEGJl-sd_hfZUqjZOE_S_UWp_Fd9QYlP2cWDvGH8vFhx2ek9KovEob5Bh2LX_Gaf7t237B34wKeN4B8aqapyTh3Q8v_Z61bDTNLyi6ZA8zcrUOgCVLVMx_EFizx31WIDZrePsSpX4bfRurcvRyvNNVdWLaS96JYog"
    }
  ]
}
```

### Step 2:  Capture and remove the digital signature from step 1

Digital Signature:

```
gXyPW--uUKvGXRh_oDC7IYlx13hGmkiQw6XX3YX_V_i4Y39OPilf0q0qf46aO3IrvG-5_fgeQ3dIunmizYneaVJKjsXo-gkJczvGDehlTjS7MBUIGyD9DRd41DnaxWWwzU-T4sZCur664_3J0C-WRCDgZxiB_ItFpeSnPJ8rR8GRFO6M9YS-ejEGJl-sd_hfZUqjZOE_S_UWp_Fd9QYlP2cWDvGH8vFhx2ek9KovEob5Bh2LX_Gaf7t237B34wKeN4B8aqapyTh3Q8v_Z61bDTNLyi6ZA8zcrUOgCVLVMx_EFizx31WIDZrePsSpX4bfRurcvRyvNNVdWLaS96JYog
```

Remaining Object:

```json
{
  "type": "playbook",
  "spec_version": "cacao-2.0",
  "id": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
  "name": "Playbook 1",
  "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
  "created": "2022-05-18T11:31:31.319Z",
  "modified": "2022-05-18T11:31:31.319Z",
  "signatures": [
    {
      "type": "jss",
      "id": "jss--af892292-c4b4-47eb-9be6-4897ff4b9388",
      "created_by": "identity--5abe695c-7bd5-4c31-8824-2528696cdbf1",
      "created": "2023-01-10T17:39:31.319Z",
      "modified": "2023-01-10T17:39:31.319Z",
      "signee": "ACME Cyber Company",
      "valid_from": "2023-01-10T17:39:31.319Z",
      "valid_until": "2023-06-10T17:39:31.319Z",
      "related_to": "playbook--a0777575-5c4c-4710-9f01-15776103837f",
      "related_version": "2022-05-18T11:31:31.319Z",
      "hash_algorithm": "sha-256",
      "algorithm": "RS256",
      "public_key": "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3watO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47RnnfR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NTkmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4EjzthkJ8IPwIDAQAB"
    }
  ]
}
```

### Step 3: Parse or fetch the public key from step 2

```
Public RSA Key E:  65537
Public RSA Key N:
21059409706530871027159923152575226016100491304035079351263921833442741931451740146712071913128794323145066705509880772966898802951179542662416048514009100169204319582186431003855440031712504682027007873576875878900968461609481876517068958782007364480404972357715060302084902771376501469371170875499194864831981063610546010391567296668298595547190243490360742271883347302484090862191539604535968402460061731217265463678666809460993311474732287058055878491599597361095237978376986522365495265225580650629373211602244516038322865322531398087185749308509197225776569239178517866302894223184683331023672630700008907147327
```

### Step 4: Create canonical version of signature object from step 2

```json
{"created":"2022-05-18T11:31:31.319Z","created_by":"identity--5abe695c-7bd5-4c31-8824-2528696cdbf1","id":"playbook--a0777575-5c4c-4710-9f01-15776103837f","modified":"2022-05-18T11:31:31.319Z","name":"Playbook 1","signatures":[{"algorithm":"RS256","created":"2023-01-10T17:39:31.319Z","created_by":"identity--5abe695c-7bd5-4c31-8824-2528696cdbf1","hash_algorithm":"sha-256","id":"jss--af892292-c4b4-47eb-9be6-4897ff4b9388","modified":"2023-01-10T17:39:31.319Z","public_key":"MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAptKZyFPStvmOlb0WihOBhlHUr6wFDHC+tW7hJAudfTQ5mHZQpB8PoMz07udZA+dG8dhUIPkmXlp1TgREeYTHdhxhuf0y/GhbpZv5JPYHx3watO+HWO2qYkjRMEcrWhPMdaVkS/Xe/liaMcow4jYoWaFm8VobeYsyVD2bWWdyl4joTEETm1Z47RnnfR15kVhVudVrDzEFmM4nXV/6dmIg184RJE4httwBFxR8qZCQCwTiJmsoyJxfUR0Gs4ePKc5sB0NTkmFZc5klQSitd67RJn2ldhbqE7EpDl4XlIt+UyLJm1guCBltia8Agke7dXuhpB7hQ6LJwY4EjzthkJ8IPwIDAQAB","related_to":"playbook--a0777575-5c4c-4710-9f01-15776103837f","related_version":"2022-05-18T11:31:31.319Z","signee":"ACME Cyber Company","type":"jss","valid_from":"2023-01-10T17:39:31.319Z","valid_until":"2023-06-10T17:39:31.319Z"}],"spec_version":"cacao-2.0","type":"playbook"}
```

### Step 5: Create a hash (SHA256 in hex) of the canonical version of playbook from step 4

```
973bb6492184e4681b1eab9df1f56926fc1a91582e3529bfd0bfb231e1c51b0a
```

### Step 6:  Verify the signature received using the public key and algorithm (RS256) from the signature object

Signature is valid
