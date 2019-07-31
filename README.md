# git-tools
Misc git related tooling


* git-restore: when git-revert-ing a previous revert, it's cleaner to label it
  as a restore and include the original commit message. This script does so.

   Add a restore of the original commit starting from a revert.
   ```
   git revert bad-commit;  # -> creates revert ABCD
   git restore ABCD;
   ```

   For a previous revert, re-render the description:
   ```
   git revert XYZ;
   # freshly created revert-of-revert is ABCD
   git-restore --rewrite-revert-to-restore-in-place ABCD
   ```

* git-slice: Rewrite history to only include changes specifically named files,
  over a specific commit range. This is probabably even more dangerous than it
  sounds.  Warning: this is from before when I figured out how to add entries
  to the reflog, so there's less safety net than you might think.

* git-split:
  Rewrite history to split changes to specific files out into their own
  commits. This only occurs in the named commit range. This is pretty safe,
  overall, given the usual caveats about rewriting history.
  ```
  git split my-too-big-change the/path/to/the/file
  ```
