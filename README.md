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
#### Recommendation for flashing new firmware
Add this combo ( change the key positions as you like ) to you keymap file to be 
able to enter bootloader mode on the dongle without having to press the physical button.    
Now by pressing the keys on the given positions simultaneously you can enter the bootloader mode.
```
        combos {
            compatible = "zmk,combos";
            // this allows for entering bootloader mode on the dongle with a key combo
            // otherwise one would have to press the very tiny reset button on the dongle
            reset{
                key-positions = <36 41>;
                timeout-ms = <100>;
                layers = <0>;
                bindings = <&bootloader>;
            };
```


