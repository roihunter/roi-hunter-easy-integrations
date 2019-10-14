# ROI Hunter Easy Integrations

## Iframe Initialization Payload

```html
<script>
    window.addEventListener("DOMContentLoaded", function () {
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
        document.getElementById('rhEasyIframe').src = iframeUrl;
    }, false);

    function onRhEasyIframeLoad() {
        // Create IE + others compatible event handler
        var eventMethod = window.addEventListener ? "addEventListener" : "attachEvent";
        var eventer = window[eventMethod];
        var messageEvent = eventMethod === "attachEvent" ? "onmessage" : "message";

        // Listen to message from child window
        eventer(messageEvent, function (e) {
            if (e.data.type === "roihunter_plugin_height") {
                // Change size of iFrame to correspond new height of content
                document.getElementById('rhEasyIframe').style.height = e.data.height + 'px';
            } else if (e.data.type === "roihunter_location") {
                window.top.location = e.data.location;
            }
        }, false);
    }
</script>
<iframe id="rhEasyIframe" scrolling="yes" frameBorder="0" allowfullscreen="true" align="center" onload="onRhEasyIframeLoad()"
        style="width: 100%; min-height: 500px">
    <p>Your browser does not support iFrames.</p>
</iframe>
```

## Plugin API

- [Order API](OrderApi.md)
- [Product API](ProductApi.md)
- [State API](StateApi.md)
- [Store Info API](StoreInfoApi.md)
