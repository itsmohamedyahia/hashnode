# How to change a Git commit date (for beginners)

# Why

I don't know what you will benefit from changing a git commit date, but a use that might come to my mind, and which I already used it for is converting a project you have been manually copying and making versions out of it like when make or do a file or a project and name it " file final" then "file final final" then "file finale" and so on like what I was previously doing before being introduced to Git to a sophisticated version control system like Git and keep original dates.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665869524256/SCRMdghta.png align="left")


# How

> From now on, I am assuming you know git commit command and its option --amend. If not, then read about them in the [docs](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---fixupamendrewordltcommitgt).

So, this is the template code:

```
git commit --amend --no-edit --date <date>
```

The Git internal format for setting `<date>` is `<unix timestamp> <time zone offset>`, where the [unix timestamp](https://www.unixtimestamp.com/) could be replaced with other time formats like:

[RFC 2822](https://git-scm.com/docs/git-commit/2.24.0#Documentation/git-commit.txt-ISO8601)

So the 7th of April, 2005 at 22:13:13 with a time zone that is ahead of UTC by 2 hours will be written like this:

`Thu, 07 Apr 2005 22:13:13 +0200` or without the `,`
`Thu 07 Apr 2005 22:13:13 +0200` or without the day
`07 Apr 2005 22:13:13 +0200` or skip the time zone altogether
`07 Apr 2005 22:13:13` or
`Fri 07 Apr 2005 22:13:13` 

> **Note:** As you may have noticed in the last example, I have written Friday instead of Thursday which you may think is a typo, but it isn't. You can write the day abbreviation wrong and it won't affect the date or be recorded falsely.

[ISO 8601](https://git-scm.com/docs/git-commit/2.24.0#Documentation/git-commit.txt-ISO8601)

`2005-04-07T22:13:13` or
`2005-04-07 22:13:13`

> **Note:** The date part (without time) could be replaced with simpler formats like these `YYYY.MM.DD, MM/DD/YYYY, and DD.MM.YYYY`.

`<time zone offset>` is just the offset in hours and minutes either ahead from or after UTC. For example, EET (which is 2 hours ahead of UTC) is `+0200`

`--no edit` option amends the commit without launching the editor since you only want to change the date and not the commit message.

So if you want to change the date to 17 Aug 2022 at 08:19:19 for example then your git command could be like this:

```
git commit --amend --no-edit --date "17/08/22 20:19:19 +0200"
```
If, for some reason, that doesn't work for you (running an old version of Git, ..etc), then you can add `GIT_COMMITTER_DATE=<date>` before the command like this:

```
GIT_COMMITTER_DATE=<date> git commit --amend --no-edit --date <date>
```

`GIT_COMMITTER_DATE` is an environment variable ([Read More Here](https://medium.com/chingu/an-introduction-to-environment-variables-and-how-to-use-them-f602f66d15fa)) in which you will set the `<date>`. An environment variable is like any variable but it affects the environment in which the program runs. Here, it kind of tricks Git into thinking it is running the commit on a different date.
