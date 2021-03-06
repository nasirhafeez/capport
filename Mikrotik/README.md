# Mikrotik External Captive Portal

This is an example of a PHP based external captive portal for Mikrotik. The code given here can be used to setup a basic captive portal featuring an HTML login form. It is based on the external captive portal code given the in Mikrotik Wiki:
```
https://wiki.mikrotik.com/wiki/HotSpot_external_login_page
```
This code will authorize the user with the username `admin` and a blank password.

The router redirecting the user can use the following `POST` parameters. Being `POST` the parameters are not displayed in the URL:

```
<form name="redirect" action="https://example.com" method="post">
<input type="hidden" name="mac" value="$(mac)">
<input type="hidden" name="ip" value="$(ip)">
<input type="hidden" name="username" value="$(username)">
<input type="hidden" name="link-login" value="$(link-login)">
<input type="hidden" name="link-orig" value="$(link-orig)">
<input type="hidden" name="error" value="$(error)">
<input type="hidden" name="chap-id" value="$(chap-id)">
<input type="hidden" name="chap-challenge" value="$(chap-challenge)">
<input type="hidden" name="link-login-only" value="$(link-login-only)">
<input type="hidden" name="link-orig-esc" value="$(link-orig-esc)">
<input type="hidden" name="mac-esc" value="$(mac-esc)">
<input type="submit" value="continue">
</form>
```

For a typical Android client the redirect parameters are shown below:

```
Array ( [mac] => 70:8A:09:65:4D:EC [ip] => 192.168.88.253 [username] => [link-login] => http://192.168.88.1/login?dst=http%3A%2F%2Fconnectivitycheck.platform.hicloud.com%2Fgenerate%5F204%5Fe45e980b-f016-4fc8-bd31-5a26de43f707 [link-orig] => http://connectivitycheck.platform.hicloud.com/generate_204_e45e980b-f016-4fc8-bd31-5a26de43f707 [error] => [chap-id] => [chap-challenge] => [link-login-only] => http://192.168.88.1/login [link-orig-esc] => http%3A%2F%2Fconnectivitycheck.platform.hicloud.com%2Fgenerate%5F204%5Fe45e980b-f016-4fc8-bd31-5a26de43f707 [mac-esc] => 70%3A8A%3A09%3A65%3A4D%3AEC )
```
