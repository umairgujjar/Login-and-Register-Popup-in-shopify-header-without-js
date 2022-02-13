# Login and Register Popup in shopify header without js

Here's code for creating popup for login and create account/register without any javascript just using css and liquid.
I wrote this code on https://knightforgestudio.com/ check it for live demo.


1. Upload login_register_popup.liquid file to your Shopify theme -> snippets

2. Upload popup.css to your theme -> assets

3. Add following 2 lines to start of your theme -> sections -> header.liquid file. 
```
  {% render 'login_register_popup' %}
  {{ 'popup.css' | asset_url | stylesheet_tag }}
```

4. and then add following line of code where you want login text in header.liquid file
```
  <a href="{%- if customer -%}{{ routes.account_url }}{%- else -%}#open-login{%- endif -%}" 
  class="menu-drawer__account link focus-inset h5 site-header__icon site-header__account">
  {% render 'icon-account' %}
  {%- liquid
    if customer
      echo 'Account'
    else
      echo 'Log in'
    endif
   -%}
</a>
```

if you feel stuck anywhere. Feel free to message me on https://www.facebook.com/MrUmairGujjar/ or send a email at umairgujjar7@gmail.com
