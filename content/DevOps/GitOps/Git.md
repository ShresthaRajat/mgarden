---
tags: [git, source-control, version-control]
title: Git
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Git
#git #source-control #version-control


Git is a distributed version control system: tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows. 

Git is a distributed version control system developed by Linus Torvalds, the creator of the Linux Kernel. Initially developed to assist in developing the Linux Kernel, Git is powerful and easy to use. It supports linear development, which allows more than one developer to work on the same project concomitantly. It is widely used for collaboration of Opensource projects such as [Linux](Cyber%20Operations/Operation%20Tools/Linux.md).￼
Again those image names need to be prefixed with mcr.microsoft.com/, and the tags are for the latest LTS release so they're moving targets - right now aspnet:3.1 is an alias for aspnet:3.1.11, but next month the same 3.1 tag will be used for an updated release.

dotnet/core/runtime:3.1 has the .NET Core runtime, so you can use it for console apps;
dotnet/core/sdk:3.1 has the SDK installed so you'll use it in the builder stage to compile .NET Core apps;
dotnet/core/aspnet:3.1 has ASP.NET Core 3.1 installed, so you can use it to run web apps (they're still console apps in .NET Core, but the web runtime has extra dependencies).
.NET Core 3.1 will be supported until December 2022; 2.1 is also an LTS release with support until August 2021, and there are images availabl