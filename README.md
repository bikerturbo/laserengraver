# LaserEngraver

Perfect extension for Inkcaps.<br>
Export gcode for laser engraving cnc.<br>
<br>
This version is without error *“AttributeError: ‘module’ object has no attribute ‘unittouu’” or “unittouu not part of inkex module“*. (http://www.tylerforsythe.com/2015/02/inkscape-laser-engraver-bug/)
```
The bug is on line 3080 of laserengraver.py and broke due to an Inkscape change.

Old line:
  doc_height = inkex.unittouu(self.document.getroot().get('height'))

New line:
  doc_height = self.unittouu(self.document.getroot().xpath('@height', namespaces=inkex.NSS)[0])
```
Now is everything OK (Inkscape 0.92.3 & Xubuntu 18.04.1 at home and w10 at work).
