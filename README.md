# Setup

```
sudo vi /etc/hosts
127.0.0.1       localhost.com
127.0.0.1       localhost.co.jp
127.0.0.1       foo.localhost.com
127.0.0.1       bar.localhost.com
127.0.0.1       foo.localhost.co.jp
127.0.0.1       bar.localhost.co.jp
```

# Procedure

```
npm i
DEBUG=myapp:* npm start
# open http://foo.localhost.com:3000/foo
# check cookie to have @Stfoo....
# execute fetch('http://bar.localhost.com:3000/bar', { mode: 'cors', credentials: 'include'}).then(res=>res.json()).then(res=>console.log(res))
# check cookie to have @Stbar....
```

# Errors

VM366:1 Set-Cookie header is ignored in response from url: http://foo.localhost.com:3000/bar. Cookie length should be less than or equal to 4096 characters.
