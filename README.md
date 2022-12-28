# apache-refuse-the-Content-Security-Policy-headers


#goto apache website configuration
that is 
#/etc/apache2/sites-available/domain.conf
and add this 

<VirtualHost *:443>
  
  Header unset X-Forwarded-Host
  ##Apache Security headers##
    Header always set Strict-Transport-Security "max-age=31536000"
    Header always set X-Frame-Options "deny"
    Header always set Permissions-Policy "accelerometer=(),autoplay=(),camera=(),encrypted-media=(),fullscreen=*,geolocation=*,gyroscope=(),interest-cohort=(),magnetometer=(),microphone=(),midi=(),sync-xhr=*    ,usb=(),xr-spatial-tracking=()"
    Header always set Referrer-Policy "strict-origin-when-cross-origin"
   Header always set Content-Security-Policy: "\
   frame-src 'self' \
     *.google.de   \
       google.de   \
     *.google.com  \
       google.com  \
;"
 
  </Directory>
