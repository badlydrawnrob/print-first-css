<details open>
<summary>Html Code Block</summary>

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html>
  <head>
    <title>A Tiny Page</title>
    <style type="text/css">
    <!-- p { font-size:15pt; color:#000 }  -->
    </style>
  </head><!-- real comment -->
  <body bgcolor="#FFFFFF" text="#000000" link="#0000CC">
    <script language="javascript" type="text/javascript">
          function changeHeight(h) {
            var tds = document.getElementsByTagName("td");
            for(var i = 0; i < tds.length; i++) {
              tds[i].setAttribute("height", h + "px");
          }}
    </script>
    <h1>abc</h1>
    <h2>def</h2>
    <p>Testing page</p>
  </body>
</html>
```

</details>
