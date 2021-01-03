---
layout: post
title: Spicing Up your GitHub Profile with HTML and CSS
images-path: /images/posts/2021-01-02-github-profile-readme
image: /images/posts/2021-01-02-github-profile-readme/cover.jpg
tags: [GitHub, SVG, Profile, "Online Presence"]
---

Last year, GitHub added a new cool feature for the user profile. You can now add a README file to it, and it will show up besides your profile pic. This is great for talking a bit about yourself and what you do, putting some contact info, or simply making a cool first impression.

## Creating the Repository

For adding this to your profile, there's a little secret. Instead of an option in your "Edit Profile" settings, this is achieved by <span class="text-highlight">creating a new repository with the same name as your GitHub username.</span>

<figure markdown="1">

![Screenshot of GitHub repository creation]({{page.images-path}}/repo-creation.jpg)

<figcaption>🎉️ Creating a new repo with the same name as your username immediatelly makes GitHub praise you for finding out this secret.</figcaption>
</figure>

You can choose to initialize the repository with a README file already. After that, the content of this file will already start showing on your personal profile.

The README is just a Markdown file, which may make you think initially that you can only write in stuff with GitHub's default styling. However, when you get creative, there's a lot more you can do. You can add images and GIFs to it, sure, but SVGs are the real heros here. By adding SVG files to the Markdown file, you enable a lot of possibilities. SVG files support HTML tags and CSS styles (including animations!)

For adding HTML to the SVG, we can use the `<foreignObject>` tag. This is an element that can include elements from different XML namespaces. Which means that even though you're in a SVG namespace, you can use XHTML elements and all the features it supports, including the `<style>` tag for adding CSS.

As an example, check out the SVG file I use to add the "tags" with technologies to my profile:

{% highlight html %}
<svg fill="none" viewBox="0 0 300 120" width="300" height="120" xmlns="http://www.w3.org/2000/svg">
  <foreignObject width="100%" height="100%">
    <div xmlns="http://www.w3.org/1999/xhtml">

      <style>
        .tags {
          display: flex;
          flex-wrap: wrap;
          height: 100%;
          width: 100%;
        }
        .tag {
          background-color: #E3FFFF;
          border-radius: 0.25em;
          color: #0ca4a5;
          border: 1px solid #0ca4a5;
          display: inline-block;
          font-size: 0.75em;
          line-height: 2em;
          margin: 0.125em;
          padding: 0 0.5em;
          text-decoration: none;
          font-family: sans-serif;
        }
      </style>

      <div class="tags">
        <div class="tag">Angular</div>
        <div class="tag">Vue(X)</div>
        <div class="tag">JavaScript</div>
        <div class="tag">TypeScript</div>
      </div>
      <div class="tags">
        <div class="tag">(S)CSS</div>
        <div class="tag">Building UIs</div>
        <div class="tag">Web Components</div>
      </div>
      <div class="tags">
        <div class="tag">Ionic</div>
        <div class="tag">Electron</div>
        <div class="tag">.NET</div>
      </div>

    </div>
  </foreignObject>
</svg>
{% endhighlight %}

From there on, the possibilities are endless. On my profile, I added my personal logo SVG and the same drawing animation used on my own website.

<figure markdown="1">

![Animation on my GitHub Profile]({{page.images-path}}/my-profile.gif)

<figcaption>Using CSS animations inside the SVG, I was able to mimic the animation on my website.</figcaption>
</figure>


Feel free to check out [the source code](https://github.com/matfantinel/matfantinel) to find out how it works.

## Inspiration

Some people have compiled [a list of amazing examples and inspirations for your profile](https://github.com/abhisheknaiidu/awesome-github-profile-readme). Some are minimalistic, others more complex, and some even get data from APIs (!). My favorite is [this one from Livio Brunner](https://github.com/BrunnerLivio), which definitely brings all the best things from 2000's web.