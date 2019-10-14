# ROI Hunter Easy Integrations

## Iframe Initialization Payload

```js
const payload = {
    profile: 'production',
    platform: 'WOO_COMMERCE',
    plugin_version: '1.0.0',
    client_token: 'abcdefgh123', // Token for Plugin API authentication
    api_base_url: 'https://mybeststore.com/api/roi-hunter-easy/v3/',
    access_token: 'cdefghi' // User authentication token issued by RH Easy, has empty value during the first start
};

const payloadBase64 = btoa(
    unescape(
        encodeURIComponent(
            JSON.stringify(payload)
        )
    )
);

const iframeUrl = `https://goostav-fe.roihunter.com?payload=${payloadBase64}`;
```

## Plugin API

- [Order API](OrderApi.md)
- [Product API](ProductApi.md)
- [State API](StateApi.md)
- [Store Info API](StoreInfoApi.md)
