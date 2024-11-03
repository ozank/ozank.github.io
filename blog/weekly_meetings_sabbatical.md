---
layout: page
title: GitHub Repos (Sabbatical Edition)
permalink: /blog/weekly_meetings_sabbatical/index.html
---


# Commit or It Didn’t Happen!

As you know, we’ll need to coordinate our work remotely for most of 2025 due to my upcoming sabbatical. To prepare for this, we’ll need to refine our communication practices and ensure a structured way to track your progress. GitHub used to be the most useful tool in our research group, and I want to make it active again. These changes will be in effect immediately, and I would like everyone to actively use their GitHub account and set up the necessary repositories as soon as possible.

<img src="../images/git_fire.png" alt="Drawing" style="width: 400px;"/>


## Create Separate Repositories for Each Project/Thesis

I’d like each major project, thesis, and paper to have its own repository. This will help keep files organized, separate timelines, and allow you to focus on one task at a time. Individual repositories are also an excellent way to back up your work and maintain a complete history of each project.

### Thesis Repositories

If you have a thesis title assigned (prior to the second semester in MSc), please create a dedicated repository for your thesis work. This repository should contain everything related to your thesis, including the manuscript (in LaTeX, for instance), experimental data, simulations, and any other relevant materials. For some structural ideas, refer to the links provided.
Remember to set up a well-defined directory structure, such as /text, /figures, and /data. This approach will keep your files organized and accessible.

- [Furkan Karakaya MSc Thesis](https://github.com/furkankarakaya/GaN-Studies)
- [Gökhan Çakal MSc Thesis](https://github.com/gkhnckl/Axial-Flux-Permanent-Magnet-Machine-with-Novel-Flat-Winding-Made-of-Conductor-Sheet)
- [Enes Ayaz PhD Thesis](https://github.com/EnesAyaz/KTH)


### Project Repositories

Every project within our research group should have its own repository. Team members assigned to a project should have read/write access to the project’s repository. Each repository will need a designated admin who will manage the file and folder structure, coordinate issues, and oversee tasks. Project repositories should be created under the ODTU GitHub account. If you need access, please reach out to the repository admin. Refer to the following repositories for examples.

- [IMMD Project](https://github.com/odtu/IMMD/)
- [WPT Motor](https://github.com/EnesAyaz/WPTMotor)
- [1001 WPT Project](https://github.com/hakanpolat/1kW-SiC-Series-Series-Compansated-Contactless-Slip-Ring-Design)
- [Fault Tolerant Drives](https://github.com/hakansrc/fault_tolerant_drives/)
- [Teaching Materials](https://github.com/mesutto/Teaching-Materials)


## Commit Small, Frequent Changes

I encourage you to make small, consistent updates by committing daily. Whenever you revise a paragraph, add a figure, or adjust your code, record it as a commit. These small, frequent contributions keep the project active and can significantly boost your motivation as you see your work evolve. Regular commits also maintain an active link between you, me, and the rest of the research team.

I expect AT LEAST THREE COMMITS EACH WEEK from everyone. It’s fine to spend some days reading papers or tackling complex problems, but this shouldn’t prevent you from making small updates—even if it’s a brief text edit or adding to your to-do list. Take a few minutes at the end of each session to commit your updates with a meaningful message summarizing the changes (useful for both me and your colleagues). That's the kind of commit history that I would like to see:

<img src="../images/commits.png" alt="Drawing" style="width: 600px;"/>

At the end of each week, I’d also like a brief [weekly report](https://github.com/odtu/IMMD/blob/master/weekly%20plan.md) (editing a markdown file is fine). This weekly report should summarize your accomplishments for the week and outline your plans for the next week. You can also track this on GitHub Projects if you prefer. 


## Guidelines:

### Public or Private?

If it is your thesis repo, I would go for a public repo, as it will give you benefit of academic networking. Similarly, if it is an academic project repo, I think a public repo would be better. However, for industry-funded projects or in academic projects where a patent/paper application is in progress a private repo is more suitable. Please consider, GitHub has a few limitations on private repos.

### Working with Large Files

I am aware that several people work on large files such as FEA files etc. Unfortunately, these type of files are not suitable for version control, but this is not an excuse to use version control.  You can still keep all your files in a folder, but you just need to create a [.gitignore file](https://www.pluralsight.com/resources/blog/guides/how-to-use-gitignore-file) (Please ask Özgür if you need help). In this case, your large files will not be send to your GitHub repo, so they will not be synced or backed-up. Please make sure you have other options -such as, [Syncthing](https://syncthing.net/), [PowerLab NAS](http://144.122.166.92:8080/cgi-bin/), Google Drive etc.- so that other team members or you (from other computers) can access these large files. Having backups of your files is your responsibility.  Remember shit happens (computers break down or  get stolen etc.) and you need to plan ahead.


### Working with Word/PDF Files

Unfortunately, Microsoft Word files are not very useful in git versioning. It is ok to put reports, papers in .docx file for submission, but I advise you to keep the updated files in plain text (.txt) or in Markdown (.md) format. For theses, papers you should use LaTeX files. Please ask team members if you are not familiar with these formats. Markdown files and README files are great to keep track and have nice visuals as GitHub website also compiles them (you can then convert them to other formats as well). You can have a look at the following links:

- [Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/)
- [Pandoc Document Converter](https://pandoc.org/)
- [Doc Templates](https://github.com/beevomit/docTemplates/tree/master)
- [README for Your GitHub Project](https://medium.com/@sumudithalanz/the-art-of-crafting-an-effective-readme-for-your-github-project-cf425a8b1580)
- [Readme Best Practices](https://tilburgsciencehub.com/topics/collaborate-share/share-your-work/content-creation/readme-best-practices/)


It is ok to put a few useful PDF files in your GitHub repos, but please use a proper reference management tool (such as [Mendeley](https://www.mendeley.com), [Zotero](https://www.zotero.org/), [Research Rabbit](https://www.researchrabbit.ai/)) for your literature reviews. There will be some periods that you spend most of your time reading papers, but even those times please take your time to write a few paragraphs to your repos about what you learnt from these readings.


If you have any suggestions, please feel free to make a [push request](https://github.com/ozank/ozank.github.io/tree/master/blog).

