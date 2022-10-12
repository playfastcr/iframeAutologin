<iframe id="MyIFrame" width="400" height="400"></iframe>
<script type="text/javascript">
    var iframeURL = 'http://mysite.com/path/applicationPage.aspx';
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
