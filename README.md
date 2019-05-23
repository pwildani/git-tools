# git-tools
Misc git related tooling


* git-restore: when git-revert-ing a previous revert, it's cleaner to label it
  as a restore and include the original commit message. This script does so.
  (currently doesn't handle the revert itself, but that should just be a
   matter of coding).
   ```
   git revert XYZ;
   # freshly created revert-of-revert is ABCD
   git-restore --rewrite-revert-to-restore-in-place ABCD
   ```

* git-slice: Rewrite history to only include changes specifically named files,
  over a specific commit range. This is probabably even more dangerous than it
  sounds.  Warning: this is from before when I figured out how to add entries
  to the reflog, so there's less safety net than you might think.
