# PREVENT-AD registered — clinical data (new LORIS API)

Mirror of `conpdatasets/preventad-registered-clinical-data`: identical file
names and identical git-annex MD5E keys (18 files, 2020-10-27 release).
Only the download URLs point to the new instance:

```
https://registeredpreventad-new.loris.ca/api/v0.0.3/projects/PREVENT-AD/data_releases/<file>
```

## Fetch

```bash
TOKEN=$(curl -s -X POST -H 'Content-Type: application/json' \
  -d '{"username":"<user>","password":"<password>"}' \
  https://registeredpreventad-new.loris.ca/api/v0.0.3/login \
  | python3 -c 'import json,sys;print(json.load(sys.stdin)["token"])')

git config annex.http-headers "Authorization: Bearer $TOKEN"
git annex get .
```
