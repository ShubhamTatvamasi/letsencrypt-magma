# letsencrypt-magma

Add API key of your domain provider.

Issue certificate request:
```bash
docker-compose run issue
```

Add the TXT record in your DNS which you received from command above:
```
Domain: '_acme-challenge.nms.orc8r.magmacore.link'
TXT value: '1MVktmqlM_0_vFUg_wywv-8gKvKRtwNPGSacxsOz2FI'
```

Verify the TXT record:
```bash
host -t TXT _acme-challenge.nms.orc8r.magmacore.link
```

Generate certificate:
```bash
docker-compose run renew
```
> You can delete `TXT` record after this.

Copy `fullcahin.cer` and `orc8r.magmacore.link.key` to your sever.

delete containers:
```bash
docker-compose down
```

get help:
```bash
docker run --rm neilpang/acme.sh
```

---

Check Certificate transparency

https://transparencyreport.google.com/https/certificates
