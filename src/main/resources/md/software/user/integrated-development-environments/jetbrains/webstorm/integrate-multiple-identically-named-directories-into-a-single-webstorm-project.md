# Integrate Multiple Identically-named Directories into a Single WebStorm Project

If you want to use WebStorm to manage a directory structure like this:

```
/a/project1/
/a/project2/
/b/project1/
/b/project2/
/c/
```

You might conceive of multiple ways of configuring these directories:

1. Open each in a separate window.
2. Create a single project at the root (i.e. /).
3. Create a single project with individually-selected directories (i.e. /a/* and /b/* but not /c/).

First, you might just open them in different windows. If the directories are mostly independent, this is probably fine. However, if you want to search for files across multiple of these directories, you will have to switch between windows, thereby incurring cognitive friction.

Next, you may consider just creating a single project at the root. In the special case where the root contains *exclusively* the directories you want to integrate, this works well. However, in the directory structure shown above, what should you do if you want to exclude the `/c/` directory (perhaps because it's unrelated or large)?

That question leads you to the third option. Individually-selecting the directories to include in a single WebStorm project is possible, though it requires some configuration. To achieve this design, you can leverage WebStorm's support for [multiple projects](https://www.jetbrains.com/help/webstorm/opening-reopening-and-closing-projects.html#ws_opening_multiple_projects) & [multiple content roots](https://www.jetbrains.com/help/webstorm/configuring-project-structure.html#adding_content_root).

Before diving into the instructions below, take note of the goal: to integrate exactly `/a/*` and `/b/*` into a single WebStorm window. By doing so, you will be able to search across all the directories and move files between them with ease. Since both `/a/` and `/b/` contain a directory named `project1` (this also applies to `project2`), WebStorm is incapable of housing both directories in a single project. You will take care to create multiple projects for housing the identically-named directories separately. Once multiple projects exist, you can add additional directories to each as content roots.

Regarding the naming of your multiple projects, most project names will be rooted at the top level as flat strings. However, there is one special case you may want to take advantage of: project names delimited by "." characters enable WebStorm to group projects by their names' common prefixes. For example, if you use a reverse-DNS-style naming scheme for your projects, WebStorm can treat them like this:

```
com.github.username1.project1
                    .project2
          .username2.project
   .company.github.username.project
```

rather than as flat names (i.e. if you use slashes instead):

```
com/github/username1/project1
com/github/username1/project2
com/github/username2/project
com/company/github/username/project
```

Armed with all of that knowledge, hopefully you can now make the right decision for your use case. Follow these instructions to configure a project as described above:

1. Open WebStorm
2. Chose **Open**
3. Choose `/a/project1`
4. Choose **WebStorm > Preferences...** (⌘,)
5. Choose **Directories**
6. Choose **Add Content Root**
7. Choose `/a/project2`
8. Choose **Open**
9. Choose **OK**
10. Choose **View > Tool Windows > Project** (⌘1)
11. Choose `project1`
12. Choose **Refactor > Rename...** (⇧F6)
13. New project name: a
14. Choose **OK**
15. Choose **File > Attach Project...**
16. Choose `/b/project1`
17. Choose **Open**
18. Choose **WebStorm > Preferences...** (⌘,)
19. Choose **Directories**
20. Choose `project1`
21. Choose **Add Content Root**
22. Choose `/b/project2`
23. Choose **Open**
24. Choose **OK**
25. Choose **View > Tool Windows > Project** (⌘1)
26. Choose `project1`
27. Choose **Refactor > Rename...** (⇧F6)
28. New project name: b
29. Choose **OK**
