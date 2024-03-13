# Paint Activity Flatpak

Paint activity creates paintings or drawings, edit images created by other activities, and create images for use by some other activities.

To know more refer https://github.com/sugarlabs/paint-activity

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.Paint.git
cd org.sugarlabs.Paint
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak -y --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.Paint.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.Paint
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.Paint.json
```