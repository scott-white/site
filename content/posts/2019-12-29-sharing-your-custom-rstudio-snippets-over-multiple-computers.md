---
title: Sharing your custom RStudio snippets over multiple computers
author: Scott White
date: '2019-12-29'
slug: sharing-your-custom-rstudio-snippets-over-multiple-computers
categories: []
tags:
  - R
  - RStudio
  - Tips
toc: yes
images: ~
draft: true
---

# Snippet Basics

RStudio has a feature that a lot of people seem to ignore (or don't know even exists): snippets!

Snippets are predefined shortcuts that when used will insert additional code into your documents within RStudio. You can activate them by using the syntax `KEYWORD + Shift + Tab`.

Depending on your RStudio settings, if you open up a .R document and type `for` you may get the following:

![snippet with dialogue box](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/snippet_dialogue.jpg)

or

![snippet without dialogue box](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/snippet_no_dialogue.jpg)

In the first case, on the right hand side of the dialogue box it says `{snippet}`. This indicates that the command `for` is a snippet. Press `Enter` and it will insert a generic for loop structure.

In the second case, with your cursor touching the right side of the `for` keyword, press the `Shift + Tab` keys.

For either of these cases you should see the following:

![snippet inserted](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/for_insert1.jpg)

If you then press the `Tab` key it will move to the second part of the snippet template.

![after pressing tab](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/for_insert2.jpg)

Pressing yet again will move you to the third part of the snippet template.

![after pressing tab a second time](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/for_insert3.jpg)


In each of these spots type in the text you want there then press `Tab` and it should move you to the following position.


There are a large number of premade snippets in RStudio. To see them go to `Tools -> Global Options -> Code entry -> Edit snippets`.

![Code global options](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/global_options_code.jpg)

The edit snippets part will be at the bottom of the Code section

![Builtin snippets](/posts/2019-12-29-sharing-your-custom-rstudio-snippets-over-multiple-computers_files/global_options_snippets.jpg)

As you can see here there are a wide variety of built in snippets. Some that are nice to have, but the really nice ones are the ones you design yourself. For example, below is a snippet that I use quite often when I'm editing .Rmd files that use a lot of images where I want to reference them. This snippet is under the Markdown tab in the Edit Snippets window.

```latex
snippet fig
	\begin{figure}[h]
	\includegraphics[scale=1]{${1:filename}}
	\centering
	\caption{${2:caption}}
	\label{fig:${3:label}}
	\end{figure}
```

So now instead of having to type all that, or even remember it, I can type `fir + Shift + Tab` and have the image entered in quite quickly.



# Syncing your snippets between computers

Creating custom snippets can save you a lot of frustration, time, and hopefully delay/prevent carpal tunnel syndrome! However, usually if you want to use the same snippets across multiple computers you have to manually add them to the RStudio program on every computer you want to use them on. This can be annoying and cause some small errors if you mistype the snippets on a different computer.

Here I will show you how to have your snippets automatically update across all computers with the help of any online cloud service like Google Drive, Dropbox, or any other that you can access from all the computers that are able to access this cloud storage. I use Dropbox because one of my computers run Linux and Google has not released a supported version of Google Drive for Linux (that I'm aware of), but Dropbox provides excellent support for it.