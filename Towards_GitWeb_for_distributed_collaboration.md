
# [Towards a #GitWeb for distributed collaboration](http://www.co-creative-recipes.cc/towards-a-gitweb-for-distributed-collaboration/)


_Git and github are great tools for [distributed collaboration and stigmergy](http://www.co-creative-recipes.cc/stigmergic-collaboration/ "Stigmergic Collaboration"). Could we apply the same principles to work collaborativelly _using our current existing platforms_ yet collaborate in a permission-less, distributed manner ?_

## The current state of the web: CMS silos & platforms overkill

In the field of [Open Social Innovation](http://www.lilianricaud.com/web-strategy/open-research/open-social-innovation-open-sourcing-social-innovation-to-promote-sharing-sustainable-social-practices/) there are several great ressources but they all use a different CMS:

*   [Bretagne Creative](http://www.bretagne-creative.net/) runs on [SPIP](http://www.spip.net/en_rubrique25.html)
*   [MoviLab](http://movilab.org/) and [Wikipedia](https://en.wikipedia.org/) run on [Mediawiki](https://www.mediawiki.org/)
*   [Outils Réseaux / MousTIC and the Archipel network](http://www.lilianricaud.com/web-strategy/case-study-how-to-co-create-a-co-creative-event/) are using [YesWiki](http://yeswiki.net/)
*   [Co-Creative Recipes.cc](http://co-creative-recipes.cc/) runs on [WordPress](http://wordpress.org/)
*   [Imagination for People](http://imaginationforpeople.org/en/) is using its own customs CMS

Although these projects are all using free licences and free/libre opens source CMS, in practice copying and modiying from each other is not straighforward and there is a silo effect.

## The Git/GitHub model

Git/[GitHub](https://github.com/) makes it super easy to make personal variants while keeping a way to share and reuse content between parallel projects (“Forks”). Linus Torvald (the creator of Git) has changed the social dynamic around forking, **turning the idea of multiple versions of a work from a cultural weakness into a cultural strength** (Read [Forking is a Feature](http://dashes.com/anil/2010/09/forking-is-a-feature.html)).

Ideally everyone should be using Git/GitHub to share content so that it can be easily reused by everyone else. In practice however there are 2 majors issues:

*   Git/GitHub is designed to work with code and although Github is more user friendly, it is still not obvious for the average publisher
*   there isn’t and there won’t be any ideal platform that suits everyone and content producers will want to keep using their existing platform

Could we apply the Git/GitHub model to the web itself and make it easy to share content between existing platform ?

Here’s a little scenario inspired by the [#indieweb](http://indiewebcamp.com/) approach.

## Imagine #GitWeb: User story

_Imagine_:

I’m on the wikipedia page for “hackathon” and I want to modify it for my own purpose. Because Wikipedia has become part of the Gitweb netwok, it feature a “fork me on GitWeb” ribbon.

[![hackathon-wikipedia-gitweb](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-wikipedia-gitweb-1024x664.jpg)](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-wikipedia-gitweb.jpg)

When I clik on this button it will import the content (title, body content, #tags, link to the originl article…) in my Co-Crative recipes site where I will be able to modify the content locally in my own WordPress install.

[![hackathon-edition-mode-gitweb](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-edition-mode-gitweb-1024x729.jpg)](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-edition-mode-gitweb.jpg)

I can add an image, text, … make my own personal version of the content.

[![hackathon-co-creative-recipes](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-co-creative-recipes-1024x596.jpg)](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-co-creative-recipes.jpg)

When I save my new content, I can decide to do a “pull request”, ie inform the original content creators that I made a new version and that they might want to update their own version by “pulling” my modifications into their page and CMS.

A versionning tool allow them to quickyl see what I have changed and decide which modifications they want to integrate.

[![hackathon-mediawiki-versionning](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-mediawiki-versionning-1024x619.jpg)](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-mediawiki-versionning.jpg)

Similarly if someone using SPIP, YesWiki or Drupal fork one of my page and save it, I get a ping/pull request telling me which page has been forked and modified and short summary of the changes.

[![wordpress-pingback-pull-request](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/wordpress-pingback-pull-request-1024x200.jpg)](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/wordpress-pingback-pull-request.jpg)

I can quickly visualize the changes using my own WordPress versionning tool:

[![hackathon-wordpress-versionning](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-wordpress-versionning-1024x686.jpg)](http://www.co-creative-recipes.cc/wp-content/uploads/2014/07/hackathon-wordpress-versionning.jpg)

Hee again I can choose to add the updates to my own branch or leave it as is.

## Approach

Here are some ideas about the practical approach that could underpin this scenario. I’m not developper, so this might need tweaking.

*   A #Gitweb network of participants should agree on standards for content to clone (title, body content, #tags, link to original content …) and free licence.
*   From this each CMS should devellop a plugin that allows the following functions:
    *   add a “fork me” button.
    *   serve XML content to vsisitor sclicking the “fork me” button.
    *   the users is asked where to import the content into (in my case WordPress) and to give its credential before being authorized to post
    *   the content is imported in a draft post where the user can edit and customize before saving it
    *   after saving the user can ping back/request pulling to the original site
    *   the site gets a list of pingback and can choose to moderate them, compare versions and eventually pick up modifications it want to add into the original article
    *   the user who forked the original content gets a notified when one of his modifications has been added back.
*   some anti-spam measures are built into the system to make it easy to weed out irrelevant notifications

## Potential applications

The aim is to overcome traditionnal [Wikis Limitations](http://www.co-creative-recipes.cc/stigmergic-collaboration/#wiki-limitations) and silos, thinking more in terms of protocol instaed of reinventing another platform:

*   [it would allow distributed stigmergic collaboration](http://www.co-creative-recipes.cc/stigmergic-collaboration/ "Stigmergic Collaboration"): distributed and permission less. No consensus required. People do their own things, yet everyone can easily reuse others people and feed from each other ideas.
*   [it would](http://www.co-creative-recipes.cc/stigmergic-collaboration/ "Stigmergic Collaboration") allows several versions and **non neutral** point of views to co-exist: instead of having one true version of a topic (imagine a controversial topic such as religion or politics), a wikipedia using #GitWeb could have several “non-neutral” points of views co-existing in parrallel, offering several version of the truth and uses could choose to read from different angles. In this mode having different radical points of views could be a feature and not a bug.

## Message in the bottle

I’m not sure how feasible this is. I had the idea in my mind for long time and to my knowledge this seems easily feasible in terms of technics. Growing a network around the idea is another thing and I’m releasing the idea in the wild hoping other can improve it or build upon it. I’ll update the article as new ideas come.
