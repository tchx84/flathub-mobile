# Flathub On Mobile

If you are looking forward to a OSTree/Flatpak/GNOME community-driven phone OS, that makes two of us but, how far are we?

Well, there are multiple projects working on the necessary technology, e.g. [Pinephone](https://www.pine64.org/pinephone/) (hardware), [PostmarketOS](https://postmarketos.org/) (sofware), [Librem](https://puri.sm/products/librem-5/) (both), and others. To my knowledge, only [Fedora on the Pinephone](https://discussion.fedoraproject.org/t/pinephone-fedora-on-mobile/17149) group is considering such goal but, are our Flatpak applications ready?

This weekend project aims to provide a bit more clarity.

## Project

Given a refurbished [Moto G4 Play](https://www.gsmarena.com/motorola_moto_g4_play-8104.php) phone and a custom postmarketOS image containing only Phosh, Terminal and Flatpak, how close can I get to my regular phone workflow?

## Criteria

1. Built with **GTK** and other GNOME technologies.
2. Main features working on a real **mobile** device.
3. Available on **flathub**.

## Evaluation

|AppId|Category|GTK|Mobile|Flathub|Issues|Notes|
|:--- |---|---|---|---|---|---|
|[org.gnome.Epiphany](https://flathub.org/apps/details/org.gnome.Epiphany)|Internet| | | | |Videos performance|
|[org.gnome.Geary](https://flathub.org/apps/details/org.gnome.Geary)|Internet| |FAIL| |Won't fit in screen| |
|[org.librehunt.Organizer](https://flathub.org/apps/details/org.librehunt.Organizer)|Documents| | | | |Only for moving files|
|[org.gnome.Documents](https://flathub.org/apps/details/org.gnome.Documents)|Documents| |FAIL| |Won't start| |
|[org.gnome.Evince](https://flathub.org/apps/details/org.gnome.Evince)|Documents| |FAIL| |Won't fit in screen| |
|[org.gnome.Fractal](https://flathub.org/apps/details/org.gnome.Fractal)|Social| | | | | |
|[re.sonny.Tangram](https://flathub.org/apps/details/re.sonny.Tangram)|Social| |FAIL| |Won't fit in screen|For non-GTK messaging applications|
|[uk.co.ibboard.cawbird](https://flathub.org/apps/details/uk.co.ibboard.cawbird)|Social| | | | | |
|[com.github.bleakgrey.tootle](https://flathub.org/apps/details/com.github.bleakgrey.tootle)|Social| |FAIL| |Won't respond| |
|[org.gnome.clocks](https://flathub.org/apps/details/org.gnome.clocks)|Information| | | | | |
|[org.gnome.Weather](https://flathub.org/apps/details/org.gnome.Weather)|Information| |FAIL| |Won't fit in screen| |
|[org.gabmus.gfeeds](https://flathub.org/apps/details/org.gabmus.gfeeds)|Information| | | | | |
|[org.gnome.eog](https://flathub.org/apps/details/org.gnome.eog)|Image| |FAIL| |Won't fit in screen| 
|[org.gnome.Lollypop](https://flathub.org/apps/details/org.gnome.Lollypop)|Audio| | | | | |
|[de.haeckerfelix.Shortwave](https://flathub.org/apps/details/de.haeckerfelix.Shortwave)|Audio| | | | | |
|[org.gnome.Podcasts](https://flathub.org/apps/details/org.gnome.Podcasts)|Audio| | | | | |
|[org.gnome.SoundRecorder](https://flathub.org/apps/details/org.gnome.SoundRecorder)|Audio| |FAIL| |Won't fit in screen|Check nightly version|
|[com.github.Johnn3y.Forklift](https://flathub.org/apps/details/com.github.Johnn3y.Forklift)|Video| | | | | |
|[org.gnome.gitlab.YaLTeR.VideoTrimmer](https://flathub.org/apps/details/org.gnome.gitlab.YaLTeR.VideoTrimmer)|Video| |FAIL| |Won't show file chooser| |
|[net.baseart.Glide](https://flathub.org/apps/details/net.baseart.Glide)|Video| |FAIL| |Won't fit in screen| |
|[org.gnome.Cheese](https://flathub.org/apps/details/org.gnome.Cheese)|Video| |FAIL| |Won't fit in screen| |
|[org.gabmus.notorious](https://flathub.org/apps/details/org.gabmus.notorious)|Utilities| | | | | |
|[com.uploadedlobster.peek](https://flathub.org/apps/details/com.uploadedlobster.peek)|Utilities| |FAIL| |Won't fit in screen| |
|[org.gnome.Calculator](https://flathub.org/apps/details/org.gnome.Calculator)|Utilities| | | | | |
|[org.gnome.Contacts](https://flathub.org/apps/details/org.gnome.Contacts)|Utilities| | | | | |
|[org.gnome.Maps](https://flathub.org/apps/details/org.gnome.Maps)|Utilities| |FAIL| |Won't fit in screen| |
|[com.github.tchx84.Flatseal](https://flathub.org/apps/details/com.github.tchx84.Flatseal)|Utilities| | | | | |
|[com.github.bilelmoussaoui.Authenticator](https://flathub.org/apps/details/com.github.bilelmoussaoui.Authenticator)|Utilities| | | | | |
|[de.haeckerfelix.Fragments](https://flathub.org/apps/details/de.haeckerfelix.Fragments)|Utilities| |FAIL| |Won't fit in screen| |

### Missing on Flathub

* [Screenshot](https://gitlab.gnome.org/GNOME/gnome-screenshot)
* [Nautilus](https://gitlab.gnome.org/GNOME/nautilus)
* [Flashlight](https://puri.sm/posts/easy-librem-5-app-development-flashlight/)
* [Usage](https://gitlab.gnome.org/GNOME/gnome-usage)

## Common pain points

|Issue|Description|Blocker|Notes|
|:--- |---|---|---|
|Won't fit in screen|The application window won't shrink enough to fit inside the device screen, or main features rely on GTK widgets that won't shrink|YES|A few attempts to fix GtkFileChooser, both for [EndlessOS](https://github.com/endlessm/gtk/commits/eos3.1) and Librem|
|Small popovers|Using popovers for menu options works great in the desktop but requires too much dexterity on small devices|NO| |
|Buttons in the headerbar|Main features require users to use the secondary hand which occludes the content and it feels awkward|NO| |

## Workflows

|Workflow|Description|Supported|Available|Missing|Notes|
|:--- |---|---|---|---|---|
|Developer|Develop Flatpak applications|YES|Terminal Flatpak| |Develop on computer, build on the phone, e.g. using ssh|
|Adopter|Interact with developers and help testing applications|YES|Epiphany Fractal Notorious Flatseal| | |
|Enthusiast|Situational use and help promote the vision|YES|GFeeds Lollypop Shortwave Podcasts| |These applications are great examples|
|Regular|Personal use for basic tasks|NO|Clocks Calculator Contacts Authenticator|Geary Nautilus Documents EoG SoundRecorder Cheese Screenshot Glide| |
|Daily|Personal use for all tasks|NO|Organizer Forklift Cawbird|Flashlight Usage Tangram Tootle Weather Maps Peek Fragments| |

NOTE: Each workflow requires the previous workflow to be supported.

NOTE: This reflects my workflows, yours might differ, and that's OK.

## Something missing?

If you have any suggestion just send a PR to [this](https://github.com/tchx84/flathub-mobile) repo.
