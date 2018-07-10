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

