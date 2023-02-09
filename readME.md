## how to start such a API project

- Python 3.10.7 or greater
- prerequsites
```bash
pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```
- A google project --> developer options should be enabled and we need a oauth app to authenticate our python code
- create a project in [project on google](https://console.cloud.google.com/) and enable frive api on that project
- now we need credentials so that python can reach our drive but before that we need to design OAuth page so it will look like google auth in browser
- ** very very important --> while creating google auth page give name as project ID or it will raise error
- ** very very important --> while creating that page we need to give correct scopes so that our python can reach drive with all permission, then only we can query this
```python
SCOPES = ['https://www.googleapis.com/auth/drive']
``` 
- once it is done its time to create credential --> create a OAuth credential and download json and rename it as credential.jason
- now the create_sercice() method will parse that credential.json to produce token.json using that we can authenticate directly to our drive 