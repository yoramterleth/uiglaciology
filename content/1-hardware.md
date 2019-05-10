---
title: Hardware
nav: true
---

# Use of Hardware
We make a distinction between the server, kennicott, which is a powerful computer in the basement of McClure, to which everyone in the group can log in, and also local computers, which might be a desktop or laptop.

An important concept is that different computers, like kennicott, can be operated from a different computer.

kennicott can be accessed via a terminal and ssh (including with putty, from a Windows machine), or, alternately it can be mounted via samba to a local computer filesystem.

Do most computing on the group server kennicott.




# OLD below

Carpentries lesson content is openly developed on GitHub by hundreds of contributors editing and discussing the materials.
For example, the SWC [Version Control with Git](http://swcarpentry.github.io/git-novice/){:target="_blank"} lesson has 100+ [contributors](https://github.com/swcarpentry/git-novice/graphs/contributors){:target="_blank"} since 2013, with about 200 discussion ["Issues"](https://github.com/swcarpentry/git-novice/issues){:target="blank"} since 2015.

The lessons are created by writing [Markdown](https://daringfireball.net/projects/markdown/){:target="blank"} files, styled by a [web template](https://github.com/carpentries/lesson-example){:target="blank"}, and hosted on [GitHub Pages](https://pages.github.com/){:target="blank"} free service.

Using these lesson outlines, workshops are organized around the world by host institutions and facilitated by Carpentries trained instructors.
Using a [template](https://github.com/carpentries/workshop-template){:target="blank"}, each workshop creates a custom home page with all the information needed for participants, and can customize the lessons. 
For example, WSU's [CEREO](https://cereo.wsu.edu/){:target="_blank"} recently hosted a [Software Carpentry workshop](https://mbrousil.github.io/2019-04-08-wsu/){:target="_blank"}.

Having these lessons hosted on the web helps active learners by providing an easy to access copy of the materials for: 

- preparation
- following along during the sessions
- later reference

## Why Open?

This approach to lesson materials highlights the value of developing Open Educational Resources in easy to modify formats--enabling teachers to adapt materials to the needs of their learners...

Open Educational Resources (OER) are *not just a free download*!

{% capture text %}<blockquote class="blockquote">
<p>Open Educational Resources are teaching, learning and research materials in any medium – digital or otherwise – that reside in the public domain or have been released under an open license that permits no-cost access, use, adaptation and redistribution by others with no or limited restrictions.</p>
<div class="blockquote-footer text-right">The William and Flora Hewlett Foundation, <cite title="Source Title"><a href="https://hewlett.org/strategy/open-educational-resources/" target="_blank">OER Defined</a></cite></div>
</blockquote>{% endcapture %}
{% include card.md text=text %}

OER are materials that are free to access and use--but are also licensed to be modified, adapted, re-mixed, and re-used in new ways. 
*Open* is the key word (see the [Open Definition](https://opendefinition.org/)).
This is the feature that makes OERs so powerful for teaching and learning--they reduce costs for students, but also enable innovation, providing instructors the freedom to flexibly adapt and enrich the learning experience.

{% capture rs %}1. **Retain** – the right to make, own, and control copies of the content (e.g. download, duplicate, store, and manage)
2. **Reuse** – the right to use the content in a wide range of ways (e.g. in a class, in a study group, on a website, in a video)
3. **Revise** – the right to adapt, adjust, modify, or alter the content itself (e.g. translate the content into another language)
4. **Remix** – the right to combine the original or revised content with other material to create something new (e.g. incorporate the content into a mashup)
5. **Redistribute** – the right to share copies of the original content, your revisions, or your remixes with others (e.g. give a copy of the content to a friend)

David Wiley, [Open Content Definition](http://opencontent.org/definition/)
{% endcapture %}
{% include card.md text=rs header="5R Permissions" %}

Enjoying the freedoms of open content instructors can:

- Improve, update, or modify to ensure the most relevant content.
- Reformat to create new derivatives appropriate for different means of consuming content such as video, audio, or websites.
- Adapt to the specific context, enabling learning materials to be responsive to your course, students needs, and pedagogy.

## Why <span class="fab fa-github"></span> GitHub?

[GitHub](https://github.com/) is a cloud [Git](https://git-scm.com/) repository hosting service, with benefits!
It provides a handy web interface for managing, editing, and collaborating on Git repositories.
Originally designed to manage large open-source software projects, its use has expanded to many other types of organizations and individuals, with over 20 million users.
Accounts are free.

Features: 

- Version control (permanently stores the history of your project)
- Friendly web platform (lowers barriers to contributors)
- Project management features (organize collaboration!)
- Large open source community (increases visibility and leverage outside contributors)

Hosting your source code on GitHub makes it easier to write, access, share, and reuse OER, ensuring the content is provided in a truly [open](https://opendefinition.org/) manner.

However, one amazingly useful GitHub feature is [GitHub Pages](https://guides.github.com/features/pages/), a free service that provides static web hosting from any repository.
Using GH-Pages removes infrastructure and cost barriers, making it a great option for teaching and learning because your web presentation and source code will be openly available from the same platform.
