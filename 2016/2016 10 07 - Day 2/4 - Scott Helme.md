# CSP STS PKP SRI ETC OMG WTF BBQ
*Modern Web Security Standards*

* @Scott_helme
* scotthelme.co.uk

---

## HTTPS

* HTTP/2
* Powerfull features
* Brotli compression
* SEO Boost

## CSP
* upgrade-insecure-requests: Tries to upgrade http to https
* report-uri: Sends you a report of violated directive (report-uri.io)

## Subresource integrity
### 3rd party trust
What happens if a CDN serves something we're not expecting (e.g. evil keylogger);

* SRI hash => Make sure the requested file matches a hash you've made of the resource

```
<script src="..."
    crossorigin="anonymous"
    integrity="sha256-[hash]">
</script>
```
