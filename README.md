# GitHub action to import GPG private key

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

**Note [5/6/2021]:** This was supposed to be a fork ([nholuongut/ghaction-import-gpg](https://github.com/nholuongut/ghaction-import-gpg)) of a fork ([nholuongut/ghaction-import-gpg](https://github.com/nholuongut/ghaction-import-gpg)) of the upstream repo. Due to the restrictions on using a sign-only key, we encountered this [issue](https://github.com/nholuongut/ghaction-import-gpg/issues/58). This is an internal action that overrides this fork until the issue is resolved upstream.
## Environment Variables

Following environment variables must be used as `step.env` keys

| Name               | Description                           |
|--------------------|---------------------------------------|
| `GPG_PRIVATE_KEY`  | GPG private key exported as an ASCII armored version (**required**) |
| `PASSPHRASE`       | Passphrase of the `GPG_PRIVATE_KEY` key if set |

## Workflow Example

```yaml
name: sign
on: push

jobs:
  goreleaser:
    runs-on: ubuntu-latest
    steps:
      - name: Import GPG key
        id: import_gpg
        uses: nholuongut/ghaction-import-gpg@v2.1.0
        env:
          GPG_PRIVATE_KEY: ${{ secrets.GPG_PRIVATE_KEY }}
          PASSPHRASE: ${{ secrets.GPG_PASSPHRASE }}
      - run: |
          touch foo.txt
          gpg --detach-sig foo.txt
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: Nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)
* [PayPal.me](https://www.paypal.com/paypalme/nholuongut)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟

