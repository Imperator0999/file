<html>
  <head>
    <title>reCAPTCHA demo: Running both v2 and v3</title>
    <script src="https://www.google.com/recaptcha/api.js?render=v3_site_key"></script>
    <script>
      grecaptcha.ready(() => {
        grecaptcha.render('html_element', {
           'sitekey' : 'v2_site_key'
        });
      });
    </script>
    <script>
      function onSubmit() {
        grecaptcha.ready(() => {
            grecaptcha.execute('v3_site_key', {action: 'homepage'}).then((token) => {
               ...
            });
        });
      }
    </script>
  </head>
</html>
    
