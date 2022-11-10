# Splunk Enterprise

Splunk Enterprise is a Paid software, for analyse and Security Operation Centers for log monitoring and security breach research.

## Developer License
[Splunk Website for Developer License](https://www.splunk.com/en_us/resources/personalized-dev-test-licenses.html?locale=en_us)

## Final Steps (Post Installation)

We provide software installed but we can't configure it for you unless required and delivered with the specific data neded for configuration.

So to finalize the Post Installation do:

```
export SPLUNK_HOME=/opt/splunk/
cd $SPLUNK_HOME/bin
./splunk start
```

Now your splunk should be accesible by web.

```
http://YOUR.IP:8000
```

## Change Splunk Web Port

Feel Free to change the port, if you want by following this guide.

1. In Splunk Web, select Settings > Server settings > General Settings from the menu.
2. Change one or more of the default ports: management port, web port, App server port, KV 3. store port
4. Click Save.
5. Restart Splunk for the changes to take effect.


If you have any issue don't hesitate to contact us, using the ticket system.