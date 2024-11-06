---
title: 
layout: intro
---
<div class="info-container">
    <div class="info-block">
        <span><span style="color:gray">Name:</span> Rusny Rahman</span>
        <span class="right-text"><span style="color:gray">Location:</span> NYC/Boston</span>
    </div>
    <div class="info-block">
        <span><span style="color:gray;">Occupation:</span> Software Engineer</span>
        <span class="right-text"><span style="color:gray;">Links:</span> <a href="mailto:rusnyrahman@gmail.com" target="_blank">e-mail</a> | <a href="https://www.linkedin.com/in/rusny-rahman-5885801b4/" target="_blank">LinkedIn</a> | <a href="https://github.com/rusny23" target="_blank">Github</a></span>
    </div>
</div>

## Hello!

I'm Rusny (pronounced Ruh-shni), welcome to my blog. I am a [programmer](https://github.com/rusny23)
who likes to read books, listen to new music, and explore NYC. I recently
graduated from Tufts University in May of 2024 with a Bachelor's degree in 
Computer Science and a minor in Engineering Management. I am interested in
cyber security, embedded software, backend web development, and application development.

<p style="margin-bottom: 40px;">You can <a href="mailto:rusnyrahman@gmail.com" target= "_blank">email me</a> if you desire. I'm happy to talk about anything.</p>


<h2 style="background-color: #2D2F31; display: inline; padding: 2px 5px;">Work</h2>

<div class = "row">
      <div class = "col-20">
        <span class="current-text">Current:</span>
      </div>
      <div class = "col-80">
        Recent Tufts University Graduate
      </div>
</div>

<div class = "row">
      <div class = "col-20">
        <span class="past-text">Past:</span>
      </div>
      <div class = "col-80">
        Embedded SWE Intern @ Draper Laboratory
      </div>
</div>

<hr class="content-divider">


<span class="current-text">Projects:</span>
<ul>
    {% for project in site.projects %}
    {% unless project.draft == true or project.series %}
    <li class="post-item">
        <a class="post-title" href="{{ project.url }}"><span><u>{{ project.title }}</u></span></a>
        <div class="post-date"><i>{{ project.date | date: '%B %Y' }}</i></div>
    </li>
    {% endunless %}
    {% endfor %}   
</ul>

