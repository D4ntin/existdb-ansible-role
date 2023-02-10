
Fixed the `Backup installed exist instance` task to use the new backup script.


Removed all occurences of `warn:no` in the `tasks` directory since they are not supported anymore.


Fixed a wrong usage of the `JAVA_HOME` environment variable and removed the hardcoded path.


Fixed 'grep' command in facts gathering script.
The old 'grep git-commit' is not sufficient anymore with `existdb6` 
and matches 2 lines of the `system.properties` file like so:
```sh
git-commit=58bdcbfc89435a6991612fb1952fd477f0801722
git-commit-timestamp=20230115125612
```
Instead I changed it to `grep 'git-commit='`.
I also changed all other occurences of greps in the `exist_major_version > 4` branch
of the file to a similar style.
