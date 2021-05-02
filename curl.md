<img src="https://www.booleanworld.com/wp-content/webp-express/webp-images/doc-root/wp-content/uploads/2018/12/curl-cover-picture-1024x392@2x.png.webp" width="300px">


### Examples commands and use api rest
https://www.baeldung.com/curl-rest

### Other examples:
get
```
curl -v http://localhost:3333/categories
```
Post 
```
sudo curl -H "Content-Type: application/json" -d '{"email":"ti3@archshop.com.br","tipo_cadastro":"inscrito"}' http://localhost:3333/subscriber
```

Post
```
sudo curl -H "Content-Type: application/json" -d '{"email":"ti3@archshop.com.br","tipo_cadastro":"contatosite","nome":"Flavio","phone":"19994306714","message":"test to send message to vmcloud, new cloud", "subject":"tst send message"}' http://localhost:3333/contactSite
```
