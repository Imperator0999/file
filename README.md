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
 name: C/C++ CI

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: make
      run: make all
    - name: make test
      run: make test   
