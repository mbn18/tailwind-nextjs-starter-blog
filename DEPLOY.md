### Deploy

### Requisite

Enroll CLoudFlare.

Install [wrangler](https://developers.cloudflare.com/workers/wrangler/install-and-update/)
```shell
yarn add -D wrangler@latest
```
**note**: wrangler is installed under `./node_modules/.bin/`

Login
```shell
wrangler login
```

Create Page (if not already exist)
```shell
wrangler pages project create epoch-blog
```

create local [wrangler conf](https://developers.cloudflare.com/workers/wrangler/configuration/) file:
```shell
name = "epoch-blog"
compatibility_date = "2025-07-11"
pages_build_output_dir = "./out"
```

```shell
./node_modules/.bin/wrangler pages deploy --commit-dirty=true
```

### push

Build the static content:
```sh
$ EXPORT=1 UNOPTIMIZED=1 yarn build
```

After the static content was created, execute:
```shell
wrangler pages deploy --commit-dirty=true
```