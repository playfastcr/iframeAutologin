# 👾[PlayFast.com](https://PlayFast.com) 
# iframe AutoLogin 


## Paso 1:
Obtener de la sesión del usuario las variables "username" y "password".


## Paso 2:
Agregar el siguiente fragmento de código en la plataforma web:

```
<iframe id="MyIFrame" width="100%" height="100%"></iframe>
<script type="text/javascript">
    var iframeURL = 'https://playfast.com/auth/sign-in';
    var iframeID = 'MyIFrame';

    function loadIframe(){
        //pre-authenticate
        var req = new XMLHttpRequest();
        req.open("POST",this.iframeURL, false, "username", "password"); //use POST to safely send combination
        req.send(null); //here you can pass extra parameters through

        //setiFrame's SRC attribute
        var iFrameWin = document.getElementById(this.iframeID);
        iFrameWin.src = this.iframeURL + "?extraParameters=true";
    }

    //onload, call loadIframe() function
    loadIframe();   
</script>
```

## Paso 3:

Enviar los parametros "username" y "password" mediante el método POST includio en el iframe. 

