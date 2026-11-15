# ACore

single file anticheat for Paper 1.21.x, built for a Lifesteal SMP.
no dependencies, no packet library, one java file.

## build

1. put ACore.java in src/main/java/dev/acore/
2. put plugin.yml and config.yml in src/main/resources/
3. build with gradle or maven against paper-api 1.21.4 (compileOnly)
4. drop the jar in plugins/

## commands

  /acore status            check count and tracked players
  /acore alerts            toggle staff alerts
  /acore exempt <player>   toggle manual exemption
  /acore violations <p>    per check violation list
  /acore debug             verbose flag logging to console
  /acore reload            reload config.yml

## punishment ladder

  5 vl  alert to staff
  half  setback (rubber band)
  max   14 day ban, ban screen with ban id, discord webhook embed

violations decay slowly, so one lag spike never bans anyone.

## known limits

event based checks cannot see packets, so TimerA/B/C measure event rate
instead of real client ticks, and HitSelect only catches sloppy versions.
the next step is PacketEvents for real packet level checks.
