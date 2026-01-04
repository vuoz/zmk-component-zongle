### Zongle ZMK Module
This contains the zmk module defintions for Zongle, a super compact nrf52833 based dongle.


### Usage in your ZMK config


#### Prerequisites
Add the following entries to your `config/west.yml`:
```diff
...
remotes:
+    - name: vuoz 
+      url-base: https://github.com/vuoz
projects
+    - name: zmk-component-zongle
+      remote: vuoz 
+      revision: main
...
```
#### Configuring the dongle
```diff
include:
+   - board: zongle
+     shield: my_keeb_dongle

+   - board: zongle
+     shield: settings_reset
...
```

