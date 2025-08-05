# simple resolution changing scripts

1440res - changes desktop res to 1440p
2160res - change desktop res to 2160p

Add to /usr/local/bin then can be used on terminal or via Steam Launch options e.g. for Guild Wars 2:
```steam
1440res ; LD_PRELOAD="" game-performance %command% -autologin -mapLoadinfo -provider Portal ; 2160res
```
This is useful for games running via proton and wayland, as Fullscreen (2160p) is too large to play Guild Wars 2 comfortably.

Both are single line scripts using kscreen-doctor thus:

To find the correct outputs use:

```fish
kscreen-doctor -o
```

This will list the modes that are available and show the output e.g.:

```fish
Output: 1 HDMI-A-1 f02c2f06-ee3e-4c75-adca-c2e3afd625d0
        enabled
        connected
        priority 1
        HDMI
        replication source:0
        Modes:  1:3840x2160@60!  2:4096x2160@120  3:4096x2160@100  4:4096x2160@60  5:4096x2160@50  6:4096x2160@30  7:4096x2160@25  8:4096x2160@24  9:4096x2160@24  10:3840x2160@120*  11:3840x2160@100  12:3840x2160@60  13:3840x2160@50  14:3840x2160@30  15:3840x2160@25  16:3840x2160@24  17:2560x1440@120  18:1920x1080@120  19:1920x1080@100  20:1920x1080@60  21:1920x1080@60  22:1920x1080@50  23:1920x1080@30  24:1920x1080@25  25:1920x1080@24  26:1280x1024@60  27:1152x864@60  28:1280x720@60  29:1280x720@50  30:1024x768@60  31:800x600@60  32:720x576@50  33:720x480@60  34:640x480@60  35:640x480@60  36:640x480@60 
        Geometry: 0,0 1920x1080
        Scale: 2
        Rotation: 1
        Overscan: 0
        Vrr: Automatic
        RgbRange: unknown
        HDR: enabled
                SDR brightness: 200 nits
                SDR gamut wideness: 0%
                Peak brightness: unknown
                Max average brightness: unknown
                Min brightness: 0 nits
        Wide Color Gamut: enabled
        ICC profile: none
        Color profile source: sRGB
        Color power preference: prefer accuracy
        Brightness control: supported, set to 100% and dimming to 100%
        Color resolution: unknown
        Allow EDR: unsupported
```
in this example:
Output = HDMI-A-1
Mode = 17:2560x1440@120

Therefore the kscreen syntax would be:

```fish
kscreen-doctor output.HDMI-A-1.mode.17
```

The scripts have had the .fish extension removed. 

Once you have copied them to /usr/local/bin you should run:

```fish
chmod +x <command name>
```

To ensure they can be executed without issue.
