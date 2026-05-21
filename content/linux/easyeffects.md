
  easyeffects -b 2   # bypass ON  (mute the chain, raw audio passes through)
  # play something, listen
  easyeffects -b 1   # bypass OFF (chain re-engaged)



You're right, I had the mapping inverted earlier — apologies. The actual EasyEffects flag
  values are:

  - 1 = bypass ON (chain disabled, audio passes through raw)
  - 2 = bypass OFF (chain engaged, processing audio)
  - 3 = query current state (prints true/false, doesn't toggle)

  So for normal operation you want:

  /usr/bin/easyeffects -b 2

  And to check the current state without changing it:

  /usr/bin/easyeffects -b 3

  Your A/B test result was correct — you correctly identified that one state mutes the EQ
  effects (bypass=1) and the other engages them (bypass=2). My earlier "-b 3 toggles" was also
  wrong; it just queries.