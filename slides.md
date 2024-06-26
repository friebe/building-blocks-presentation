---
layout: cover
mdc: true
transition: fade-out
growSeed: 3
title: Components for building structured code versioning 
---

# Components for building structured code versioning

Ensuring stability and efficiency

---
growSeed: 5
layout: two-cols
layoutClass: flex items-center
---

<!--
Okayish Cliffhanger:
In the morning I saw by chance already existing articles in Confluence, so I think a few strategies are also known, so this presentation serves more or less the awareness of the importance for these strategy or mythology's
-->

<template v-slot:default>

![](/intro.png){.w-70.h-70.ml-10.mr-3}

</template>
<template v-slot:right>

# Jan Friebe

- 32 years old
- live in NRW

Full Stack developer with passion for Frontend stuff<br>
JavaScript/TypeScript // Vue // React // CSS // Design<br>

<div my-10 w-min flex="~ gap-1" items-center justify-center>
  <div i-ri-user-3-line op50 ma text-xl />
  <div><a href="https://jan-friebe.de" target="_blank" class="border-none! font-300">jan.friebe.de</a></div>
  <div i-ri-github-line op50 ma text-xl ml4/>
  <div><a href="https://github.com/friebe" target="_blank" class="border-none! font-300">friebe</a></div>
  <div i-ri-twitter-x-line op50 ma text-xl ml4/>
  <div><a href="https://twitter.com/jan_friebe" target="_blank" class="border-none! font-300">jan_friebe</a></div>
</div>
</template>

<!--
A short intro from myself...I
For more information about me you can follow these contact icons :)
-->

---
---
# The main blocks at a glance

1. Branch strategy
2. Branch naming
3. Approval System
4. Semantic commit message
5. Tags
6. Lifecycle examples

<!-- 
These are some or at least the best topics (in my opinion) to implement structured and efficient code versioning in teams, so let's take a look at what these blocks mean.
But one hint you can also use this components if are a one man show. It is a general approach for all devs. Ok, lets go...
-->

---
layout: cover
---

<h1 important-text-5xl>One branch strategy</h1>

<div text-white:50 text-2xl v-click>
<div text-yellow2 italic>Dont get me wrong here, its totally fine to work with one branch if you are alone or your team have a very very strong communication (difficult)</div>
</div>

<!-- What exactly does it mean ?
Well, the One branch strategy means you have only one branch (mostly named main) to work on for everything like features, bugs, releases, hotfixes and so on. For example if you are working in a team every developer works on this branch and do pulls, pushes and commit changes every day...
So perhaps you can already guess why it's not a good idea to have only one, but anyway i will show you the disadvantages on the next slide -->


---
---

# Disadvantages to work with one branch

<ri-close-fill class="text-red-600 text-xl" /> Conflicts with simultaneous changes<br>
<ri-close-fill class="text-red-600 text-xl" /> Difficulty in tracing changes<br>
<ri-close-fill class="text-red-600 text-xl" /> Delays in deploying updated<br>
<ri-close-fill class="text-red-600 text-xl" /> Lack of flexibility<br>

<!-- 
To work with only one have many disadvantages and here a are few.

I think every developer knows the first point, when several team members are working on different functions at the same time and someone changes a function that your code depends on. Then whoever checks-in their code first wins. This can eventually lead to conflicts and other time consuming side effects in different ways.

The next one says it can be callenging to trace changes or reconstruct the code base if anything is broken, because maybe there are also new features in the main, so a easy rollback isnt easy anymore.

I think these nex point is explained very well by the previous one. It is difficult to separate features or bugs in only one branch. So a deploying is delayed and not so fast as it should be.

And to conclude, a single branch restricts you enormously and reduces efficiency, because you always have to watch what you are doing if you deliver your changes. 

So a better solution for fix all these issues would be work with multiple branches!
-->

---
layout: cover
---
# Multiple branches strategy (feature branches)

- dev (developmet - feature, refactoring, bug(no hotfixes), docu changes...)
- main (customer build - snapshot like)

<span v-click v-mark.highlight.lime.op8.delay200 inline-block p3 mx--2>For all new features, bugs, tests, experiments and so on you should create an isolated new branch!</span>


<!--
As the name says here we have two important branches to branch off.
But I will go one step back, first we should look on the beginning of the strategy and understand ist completely.

So the DEV branch represents the status of active development. It includes new feautures , code refactoring, rewrites and so on.

So everytime u develop new things or make things that customers should not see yet because it is a future task or so, u branch off from DEV. Furthermore it could also be that the dev branch is not stable and thats ok for some time. In summary the DEV branch is the "playground" for all devs and nobody should be afraid to make anything wrong. One hint here, the dev branch is not delivered to the open world, so feel free to play with. ;) 

But don't get me wrong, if there is an automatic test deployment action behind the dev branch, then the branch should already be stable so that nobody gets into trouble.

And on the oppsite stands the Main branch which is the delivered build to the customers or the image for reference in other products as dependency. When we make an hotfix for example we should branch off from Main. And this should be ever ever be stable :)

Click - So, one golden rule is....

Maybe you have in mind now....
Oh, damn, now we have a huge pile of different branches and don't even know which one is for what anymore. You also ask u, how can i keep an overview of all this ?

Well, short answer here is categorize it!
-->

---
layout: cover
---

<h1 important-text-5xl>Categorize your branches</h1>
<span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">features</span>
<span class="bg-gray-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">bugfix</span>
<span class="bg-gray-100 text-yellow-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">release</span>
<span class="bg-gray-100 text-red-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">hotfix</span>
<span class="bg-gray-100 text-pink-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">experiment</span>
<span class="bg-gray-100 text-blue-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">username</span>
<span class="bg-gray-100 text-orange-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">docs</span>
<span class="bg-gray-100 text-violet-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">config</span>
<div v-click delay200="1" origin-top-left rotate-12 i-emojione-monotone:thinking-face w-5em h-5em absolute top-25 right-25></div>

<!--
Here you can see some categories that I find useful and that have more or less become established in the open source sector as well. You see a list of the prefixes or the groups that you add to your branches for a specific purpose.

CLICK

Confused, in the next step, I'll show you an example of what it might look like
Ok, so here u see  
-->

---
---
# Prefix your branch names
- feature/user-authentication
- bugfix/123-fix-login
- release/v1.0
- hotfix/v1.0-security-fix
- experiment/user-interface-redesign
- docs/update-readme
- config/update-env-variables

<!--
So now i think it is clear to everyone what i mean with categorize.
Perfect. Now I would like to go one step back to emphasize the advantages to work with so many branches either it looks a lot. I think it is important to understand it and realizes also the advantage that it brings in terms of speed. 
-->

---
---
# Advantages to work with multiple branches

<ri-check-fill class="text-green-600 text-xl" /> Isolation of changes<br>
<ri-check-fill class="text-green-600 text-xl" /> Collaboration<br>
<ri-check-fill class="text-green-600 text-xl" /> Code reviews<br>
<ri-check-fill class="text-green-600 text-xl" /> Feature development<br>
<ri-check-fill class="text-green-600 text-xl" /> Bug fixing<br>
<ri-check-fill class="text-green-600 text-xl" /> Experimentation<br>

<!--
So the first one is very clear i think, if u work in separate branches ur code is isolated, so there can happen no side effects from other members and their changes. So as i said before The main is every time stable and your team can also works on features. So Win win.

Feature branches must be merged back in the main code, so anyone should look over ur code via a PR and give feedback. Also other members can check out ur branch, can support u and commit changes only in ur branch.

I think i explained it well in the previous one. But additional, Code reviews helps to ensure the code quality and consistency of written code.

Well i said it often before, u can work isolated and only for u. This approach also allows better organization and management because u can split anything in backend, frontend or what even make sense.

For Bugs u make a separate branch so it allows u to make change without disrupt the feature development.

And last but not least, you don't have to worry about changes if u have a own experimentation branch.


-->
---
layout: cover
---
# 
<h1 important-text-5xl>
 Approval System</h1>
<div text-white:80 text-2xl v-click>
A feature that allows devs to review and approve changes (pull request) made by others before merging them into the main codebase
</div>

<!--
So in other words a second pair of eyes looks at your code and give feedback. 

I think that point can be a separate topic, because there's a lot to be said or a lot what i can say from my past about writing good comments to code which another written. So that the author doesn't feel offended.

But however, at another time so now we look to the advantages of this system
-->

---
---
# Advantages to work with the approval system

<ri-check-fill class="text-green-600 text-xl" /> Code quality<br>
<ri-check-fill class="text-green-600 text-xl" /> Knowledge sharing<br>
<ri-check-fill class="text-green-600 text-xl" /> Consitency<br>
<ri-check-fill class="text-green-600 text-xl" /> Risk mitigation<br>
<ri-check-fill class="text-green-600 text-xl" /> (Alignment with requirements)<br>
<ri-check-fill class="text-green-600 text-xl" /> Team collaboration<br>
<ri-check-fill class="text-green-600 text-xl" /> Continuous improvement<br>

<!--
So that the system requires a look from another on ur code, helps a lot to write high quality code and catching potential bugs early. 

You learn from others because u see code from another guy with other knowledge level. Summarized I see MRs like a forum for discuss different approches, share insights and provide feedback to improve code. This is how i got to know the system

I don't think I need to explain the next one.

Risk mitigation means reviewers can identify bugs, edge cases or side effects and addresses them before merging. So also very clear i think

The phrase in paretenthis means that a reviewer had a look if u you change only code within your scope and what the project requirements say and fulfills the acceptance criteria of the story/task whatever. So an appeal to you or a tip from me, keep the PRs small ;)

The next two are clear in my opinion and everyone can imagine what they mean.

You see i am a huge fan of working with multiple branches :)
-->

---
layout: cover
---

<h1 important-text-5xl>
  Semantic commit messages</h1>
<div text-white:80 text-2xl v-click>
Commit messages follow a structured format that conveys meaningful information about the changes
</div>

<!--
And again we categorize our names in this case the commit messages.
-->

---
layout: cover
---

<h1 important-text-5xl>Categorize your commit in msg types</h1>
<span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">feat</span>
<span class="bg-gray-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">fix</span>
<span class="bg-gray-100 text-yellow-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">docs</span>
<span class="bg-gray-100 text-red-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">style</span>
<span class="bg-gray-100 text-pink-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">refactor</span>
<span class="bg-gray-100 text-blue-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">test (adding or modifying test)</span>
<span class="bg-gray-100 text-orange-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">core (other changes related to build e.g. maintenance tasks</span>

<!--
As in the Categorize branches chapter, the division rule also applies here but in a modified way. And it highly depends on a team agreement what are the types. So this is only an example.
-->

---
layout: cover
---

<h1 important-text-5xl>
  Structure of a message</h1>
<div flex flex-col text-white:80 text-2xl>
<p>1. Type</p>
<p>2. Scope (context of the change e.g. module name)</p>
<p>3. Short summary (changes that have been made e.g. remove if clause)</p>
<p>4. Longer description (optional)</p>
</div>

<!--
So every message have a structure as following. On the next slide I show you an example how it could look like.
-->

---
layout: cover
growSeed: 4
---
# Message example

```bash
feat(user-authentication): Add OAuth2 login functionality
Implement OAuth2 authentication using Google Sign-In Api
- Configure OAth2 client Id and secret
- Add login button to the user
```

<div class="text-white:60 flex flex-col">
  <div>type = feat</div>
  <div>scope = user-authentication</div>
  <div>short summary = Add OAuth2 login func</div>
  <div>Longer description = Detailed description & bullet points</div>
</div>

<!--

-->

---
layout: cover
---

<h1 important-text-5xl>
Tags</h1>
<div text-white:80 text-2xl v-click>
Tags are like a snapshot feature to mark a specific point, denote a milestone or a delivered build. No more and no less. Easy.
</div>

---
---

# Lifecycle of a feature branch

1. Create a feature branch
2. Implement the feature in code base
3. Commit your changes (semantic commit messages)
4. Iterate and refine (fix bugs, refine your code)
5. Test your feature (unit tests, manuel testing)
6. Review and collaboration via PR (feedback of others)
7. Merge the feature branch into main
8. Be happy
9. Cleanup - delete merged feature branches

<!--
So now i talked so much that u forget the proceed. So here is a short example a summary.
-->

---
---
# Lifecycle of a release branch

1. Create a release candidate branch
2. Feature Freeze
3. Bug fixes and stabilization
4. Testing
5. Feedback and iteration
6. Documentation and release notes
7. Code review and approval
8. RC builds
9. Final testing
10. Release

<!--
And last but not least an example of the way on rc.
-->

---
layout: end
---
