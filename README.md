# simple resolution changing scripts

1440res - changes desktop res to 1440p
2160res - change desktop res to 2160p

Add to /usr/local/bin then can be used on terminal or via Steam Launch options e.g. for Guild Wars 2:
```steam
1440res ; LD_PRELOAD="" game-performance %command% -autologin -mapLoadinfo -provider Portal ; 2160res
```
This is useful for games running via proton and wayland, as Fullscreen (2160p) is too large to play Guild Wars 2 comfortably.
