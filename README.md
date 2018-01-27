# RestoreWindows
This fork of [RestoreWindows](https://github.com/gurrhack/RestoreWindows) maintains
the original functionality but also seeks to fix a screen problem affecting a number
of fullscreen applications such as Kodi and MediaPortal.

So as well as doing what RestoreWindows does (tracking window placements and restoring
them when display connections are back to normal) it also, upon waking up, forces
windows into the foreground by pressing the windows key, then restores the previously
Foreground Window.

## Why?
There appears to be a defect in Windows 1709 Fall Creator's Update which results in
DirectX fullscreen applications not waking up when displays are reconnected. Examples
of the problem [here](https://forum.team-mediaportal.com/posts/1232256/),
[here](https://www.geekzone.co.nz/forums.asp?forumid=45&topicid=223808&page_no=4#1889676)
and [here](https://forum.kodi.tv/showthread.php?tid=323398)

# Original notes
A process that tracks window placements and restores them when display connections are back to normal

When a monitor connected with either DisplayPort or HDMI is turned off, it's
disconnected from Windows as if the cable was removed (this behaviour depends
on both monitor model, graphics card, and drivers)

This utility continually tracks the position and size of desktop windows and
restores them to their correct placement when all monitors are reconnected to
the system.

```
Usage: RestoreWindows [OPTIONS]
  
  --delay t       The time in milliseconds between display reconnect and
                  window restoration. Defaults to 1000  
  --debuglog      Writes a debug log to RestoreWindow.log
```
