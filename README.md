# BasicGimpTheme
If you already gave it a go to create a theme for GIMP
you surely noticed already it's a real butthurt to figure out
the propper `widget`, `class` or `widget_class` for the control you want to edit.  
And each time you think you figured out the correct selector it's causing your whole GIMP to look completely fucked up...

For that reason I decided to create this repo.

This is a basic GIMP-theme that contains selectors for **every single control existing in GIMP**!  
This will make it easy to you to edit GIMPs Look & Feel thoroughly.

If you're not sure how to edit gtkrc-files head over to the [gtkrc-documentation](https://wiki.gnome.org/Attic/GnomeArt/Tutorials/GtkThemes).

Have a look at the different files included into this file in order to learn how to edit the theme of every single control in GIMP.  
Use the "Test"-style in order to try out your own selectors at the end of the file - for example:

```gtkrc
widget_class "<GimpDockable>*<GtkButton>.<GtkLabel>" style "Test"
```

which will only apply labels inside of buttons located inside a dockable dialogue (for example "Tool Options"-dialogue).

## Important Notice
Due to GTK's behaviour the different style-definitions need to be loaded in the correct order.  
So please do not change the order of the `include`s and keep following in mind:
  * Buttons need to be defined **before** TreeView-Buttons, Combo- and CheckBoxes
  * TextBoxes need to be defined **before** UpDownBoxes
  * UpDownBoxes need to be defined **before** Sliders