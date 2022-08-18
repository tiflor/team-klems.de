# team-klems.de

I decided to host this hugo page on netlify because I stumbled about comments that netlify has a great user experience and so far it looks quite promising.

## create new page

To create a new page this command might be handy.

```bash
hugo new content/posts/<year>/<month>/<title>.<language>.md --kind posts-<language>
```

This page contains two languages german and english, therefor content might be created two time, once in german and another on in english.
Currently I am not sure if this pays off, but I will give it a try.
Hugo seems to have some unexpected behavior at least for me so I decided to but everything in single content directory and separate the languages by file name.
Hope that will work out.
