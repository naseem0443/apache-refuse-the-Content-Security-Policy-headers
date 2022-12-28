# apache-refuse-the-Content-Security-Policy-headers


#goto apache website configuration
that is 
#/etc/apache2/sites-available/domain.conf
and add this 

<VirtualHost *:443>
  
  <br>Header unset X-Forwarded-Host </br>
  ##Apache Security headers##
    <br> Header always set Strict-Transport-Security "max-age=31536000"</br>
    <br>Header always set X-Frame-Options "deny"</br>
   <br> Header always set Permissions-Policy "accelerometer=(),autoplay=(),camera=(),encrypted-media=(),fullscreen=*,geolocation=*,gyroscope=(),interest-cohort=(),magnetometer=(),microphone=(),midi=(),sync-xhr=*    ,usb=(),xr-spatial-tracking=()"</br>
    <br>Header always set Referrer-Policy "strict-origin-when-cross-origin"</br>
   <br>Header always set Content-Security-Policy: "\
   frame-src 'self' \
     *.google.de   \
       google.de   \
     *.google.com  \
       google.com  \
;"
 
  </VirtualHost>
