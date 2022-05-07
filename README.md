
# Git

## Add sertificates to config

```
# global sertificate to work with GitHub without writing credentials every time
git config --global http.sslCAInfo /home/pasa/Job/git-certs/github-com.pem

# locally for certain repo
git config http.sslCAInfo /home/pasa/Job/git-certs/private-repo.pem
```

## Delete removed origin branches locally

```
git fetch -p
git branch -vv | grep "gone" | awk '{print $1}' | xargs git branch -D
```



# PyPI

## push package

```
# cd setup.py location 
python setup.py develop
python setup.py sdist
python setup.py bdist_wheel
twine upload dist/* --skip-existing
```
