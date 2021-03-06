# RCS18 - Notes

- [Monday](#monday)
  * [A software development workflow for academic research — Wenzel Jakob (EPFL)](#a-software-development-workflow-for-academic-research--wenzel-jakob-epfl)
  * [The philosophy of reproducible quantitative methods — Christie Bahlai (Kent State University)](#the-philosophy-of-reproducible-quantitative-methods--christie-bahlai-kent-state-university)
  * [Research from an engineering viewpoint: Software development process and best practices — Filip Pavetić (Google)](#research-from-an-engineering-viewpoint-software-development-process-and-best-practices--filip-paveti%C4%87-google)
  * [Advanced git workshop — Sourabh Lal (EPFL, GitHub Campus Expert)](#advanced-git-workshop--sourabh-lal-epfl-github-campus-expert)
  * [Tools for reproducible research (Workshop) — Tim Head (Wild Tree Tech)](#tools-for-reproducible-research-workshop--tim-head-wild-tree-tech)
- [Tuesday](#tuesday)
  * [Introduction to the Renku platform — Eric Bouillet (SDSC)](#introduction-to-the-renku-platform--eric-bouillet-sdsc)
  * [The journal as a medium for publishing software — Kate Keahey (University of Chicago)](#the-journal-as-a-medium-for-publishing-software--kate-keahey-university-of-chicago)
  * [Automatic tools for reproducible research — Kate Keahey (University of Chicago)](#automatic-tools-for-reproducible-research--kate-keahey-university-of-chicago)
  * [Techniques and guidelines for reporting reproducible and statistically sound result — Torsten Hoefler (ETH Zürich)](#techniques-and-guidelines-for-reporting-reproducible-and-statistically-sound-result--torsten-hoefler-eth-z%C3%BCrich)
  * [Data management in research — Ana Sesartic Petrus &amp; Malin Michelle Ziehmer (Digital Curation Office, ETH Zürich)](#data-management-in-research--ana-sesartic-petrus--malin-michelle-ziehmer-digital-curation-office-eth-z%C3%BCrich)
  * [Practical data management — Anna Krystalli (University of Sheffield)](#practical-data-management--anna-krystalli-university-of-sheffield)
- [Wednesday](#wednesday)
  * [Publishing and maintaining open data — Bastian Greshake Tzovaras (OpenSNP, OpenHumans)](#publishing-and-maintaining-open-data--bastian-greshake-tzovaras-opensnp-openhumans)
  * [Tools for reproducibility in Statistics and Machine Learning — Heidi Seibold (LMU Munich)](#tools-for-reproducibility-in-statistics-and-machine-learning--heidi-seibold-lmu-munich)
  * [How to write a <del>perfect</del> <em>pretty good</em> reproducible paper (Workshop) — Christie Bahlai (Kent State University) &amp; Anna Krystalli (University of Sheffield)](#how-to-write-a-perfect-pretty-good-reproducible-paper-workshop--christie-bahlai-kent-state-university--anna-krystalli-university-of-sheffield)
- [Thursday](#thursday)
  * [Team 1](#team-1)
  * [Team 2](#team-2)
  * [Team 3](#team-3)
  * [Team 4](#team-4)
  * [Team 5](#team-5)
  * [Team 6](#team-6)
  * [Team 7](#team-7)

# Monday 

[back to top](#rcs18---notes)

## A software development workflow for academic research — Wenzel Jakob (EPFL)

Academic software dev. -> experimental -> facing trade-off between two extremes: prototyping (innovation) and engineering (impact). Is it possible to have best of both?

Classic model -> Optimizing near-term outcomes -> code ends in a paper (and in cold storage)
technical dept leads to bankrupcy

New model -> longer term outcomes -> Good engineering practices -> specification (before coding) documentation (during) automated tests, continuous integration (with the help of social platforms for software projects (GitHub, Bitbucket))

This talk is a tentative cost-benefit analysis of adopting industrial engineering practices

### (perceived) costs
- time to write documentation
- lowere agility

### (perceived) benefits
- higher impact?
- might allow to reuse bits for other project

### Seven Suggestions
1. make it easy to build (complex dependencies make it difficult for people to start using your project -> low adoption) / easy / large benefits
2. modularize the codebase (extract parts that could be valuable to others and make them their own projects, needs to be "polished" enough to attract initial users) / easy /small (medium) benefits
3. At least rudimentary documentation / hard, takes time / large benefits
4. Python bindings for everything (seamless connection between python and c++) (useful because python isn't built for certain things so can take advantage of speed in c++) / medium / large benefits
5. Interactive development style (Jupyter notebook) / little time / large benefits
6. Automated tests (allows to make sure past projects still work after major improvements, especially from external contributors -> as an insurance policy, flags problems just after things were changed, so still fresh and easy to fix) / takes time / large benefits
7. Continuous integration (automatic testing of code after changes, ex: Appveyor, Jenkins. Bots post through Slack, email) / easy / large benefits

### Conclusion
- Cost-benefit to improving your development: usually time-intensive at the beginning but pays off a lot later. 
- maintainable codebase for future projects
- very motivating to see others use the code and potentially commercial applications
- good for other metrics as well (citations, etc.)

## The philosophy of reproducible quantitative methods — Christie Bahlai (Kent State University)

Slides: https://docs.google.com/presentation/d/1SvHPecp7UgOC0HENRlTHbfCfSyVP_Kayiq-FvdPpx_c/edit?usp=sharing

Past: Traditional science: Chemist working with a beaker, alone in a lab where no one can scoop their results.

Today: Open Science! Gaining more and more interest. But it's new, so lots of pushback from older faculty and people that feel that they have a system that works already.

Why people don't adopt open practices?

Lab focused on quantitative ecology, developing methods and data infrastructres for citizen science, and how can this be used

Layers of complexity in a field that wasn't designed to deal with this -> training is not adapted

People think science is independent from culture, but the reality is that science was shaped by cultural elements. The weight of paper as the record is holding back the adoption of a lot of digital technologies.

Science myths: The stereotypical view of the scientist is that of a lone cowboy. Specific research fields are seen as isolated aggregations, where outsider culture is deeply ingrained.

Education

A guidebook to take students from data collection to a reproducible publication workflow.

https://cbahlai.github.io/rqm-template/

semester project -> [preprint](https://www.biorxiv.org/content/early/2016/11/05/074633) -> picked-up by Science mag -> publishing in "traditional" journal format (in [Royal Society Open Science](http://rsos.royalsocietypublishing.org/content/3/12/160712)). More [here](https://storyengine.io/christie-bahlai/)

Make expectations clear -> share a policy -> enforcing? (still unsure how..)

## Research from an engineering viewpoint: Software development process and best practices — Filip Pavetić (Google)

Slides: 

Software development process: write code -> code review -> commit

**Code style guides** are important for functioning software. Applying them can avoid falling into obscure bugs which are part of language specifics. Consistent styles reduce learning time for new engineers, or for engineers switching projects.

Style guide is enforced by pre-commit hooks, that disallow commit if the changes do not comply with the guide.

Access to the entire codebase is systematically given to engineers. Everyone is encouraged to report bugs and submit fixes, even beyond project boundaries.

**Mutation testing**'s underlying assumption is that if you have good tests and make random changes to the code something should start failing. Used at Google to help create better tests. https://github.com/mutpy/mutpy a Python library to do this.

**Load testing** Done in a testing environment to identify any regressions in performance/efficiency

Modularity - ideally want to be able to work independently on different parts while still being sure that these will work together. Making the crucial components interchangeable, easy to modify or improve behaviour down the road.

Can divide the development in three phases, where quality should increase at each step
1. Prototyping - not too much concern of code complexity, ex: allow glue code
2. Experiment - validate the approach
3. Production - code rewrite: reduce complexity, improve testability, modularity

How review is organised at Google. 3 approvals needed to get code accepted:

1. Project owner give feedback on the relevance
2. Readability reviewer comments on the language
3. General reviewer commetn on correctness

## Advanced git workshop — Sourabh Lal (EPFL, GitHub Campus Expert)

Git Cheatsheet: https://education.github.com/git-cheat-sheet-education.pdf

Slides: https://docs.google.com/presentation/d/1jb3UTDrMLxDW5OLPh4Y4SgISr6cM0tDH_CxaiHoOuSQ/edit?usp=sharing

Open source video: https://www.youtube.com/watch?v=Tyd0FO0tko8

GitHub flow - try it out here: https://github.com/sourabhlal/github_flow_demo


## Tools for reproducible research (Workshop) — Tim Head (Wild Tree Tech)

💡💡💡 Please bring your (charged) laptop 💡💡💡

* Repository for the workshop: https://github.com/betatim/reproducible-science-tools
* [Intro slides](https://cdn.rawgit.com/betatim/reproducible-science-tools/06b69d80/slides.html?p=slides.md), apparently with some rendering bugs :(
* [Notes for the workshop](https://github.com/betatim/reproducible-science-tools/blob/7b1b0644ec5feae1bbb6dcf4250210be2042ac47/tools.md)

### `requirements.txt`
```
pandas==0.23.4
matplotlib==2.2.3
```

### Add to bikes.py
Instead of 
```
import matplotlib.pyplot as plt
```
do 
```
import matplotlib
matplotlib.use("agg")
import matplotlib.pyplot as plt
```

### Questions

Can one update the git repository while binder instance is running on the same repository? 

- Yes, as long as dependencies do not change. You can commit new changes and push them, then pull them from the binder instance to update the repository. When dependencies change one needs to restard the binder instance. 


# Tuesday 

[back to top](#rcs18---notes)

## Introduction to the Renku platform — Eric Bouillet (SDSC)

Big data also means lots of bad data.

[Renku on GitHub](https://github.com/SwissDataScienceCenter/renku)

City analytics data - Big Data does not equal good quality. Ex: speeds of vehicles > 300 km/h, vehicle locations in rivers

Large gap between data scientists and domain experts - language and vocabulary is vastly different, communicating across this boundary isn't trivial

Challenge: many machine learning models not interpretable for humans -> research on interpretable AI

Prinicpals:
- Data: FAIR
    - Findable
    - Accessible
    - Interoperable
    - Reusable
- AI: FATES
    - Fairness
    - Accountability: who takes responsibility for a decision
    - Transparency: why a decision is made
    - Ethics
    - Security, Safety
- GDPR
    - General Data Protection Regular
    - Includes needing consent to use someone's data, right to access your data, right to be forgotten, data portability, breach notification, penalties per infringement.

**SDSC** Joint venture ethz, epfl. Goals:
Close gap between data scientists, domain experts and data providers

FAQs in data-driven research
- Where does a model come from?
- How do you run it?
- Access rights: can I se this data, your code, on your computer/cloud ? Can I analyze your confidential data?
- Who is using my data, am I credited?
Answering these, follows best (open) practices

Renku tech
- Core based on git, gitlab, jupyter and docker
- [JSON-LD](https://json-ld.org/) to link data and [CWL](https://www.commonwl.org/) to describe workflows
- Can deploy on kubernetes
- Can be open or independent (self-hosted), public preview on [renkulab.io](https://renkulab.io/)

### Questions
Many fields already have their own platform, why build another?
- The goal is to cater to as many needs as possible. One of the key features of Renku is the knowledge graph, extracting links between data and processing steps, even as they move between labs, groups or data providers

How can I use the Renku platform with closed data?
- renkulab.io is in beta and open to anyone, however not currently recommended to put sensitive data on it. Other possibility is to deploy yourself (kubernetes)

Which programming languages are supported?
- Python, R, Julia supported by default, can support any other languages using dockerfiles

## The journal as a medium for publishing software — Kate Keahey (University of Chicago)

Software is underrated as a scientific instrument. It is an original scientific contribution as well. Let's give credit to software developers as well.

[SoftwareX (on Elsevier)](https://www.journals.elsevier.com/softwarex)
What does a SoftwareX article look like?
- Short article: summarised form of "classical" journal article
- Metadata table: info on the software and some metrics/graphs
- Permanent link to a code repo
- The software articles are judged on impact, not code quality/reproducibility. Reviewers not expected to run code.
- Actual software/data is published.

[Journal of Open Source Software (JOSS)](https://openresearchsoftware.metajnl.com/)

There is a difference between having enough code to reproduce a results, and a general-purpose tool to be used and extended.

Publishing software (as a specific implementation of a given algorithm) is a way to give credits to the developers of the software and to value their time and efforts to contributes to science.

[...](https://xkcd.com/2025/)

### Questions
In the computer science field, it's not unusual to publish a paper about a new piece of software, how does this relate to SoftwareX?
- There are two aspects to software, the theory behind it and it's an actual implementation. Same difference as a blueprint for a tool (theory) and a working tool (software). Makes sense to publish both in appropriate journals.

## Automatic tools for reproducible research — Kate Keahey (University of Chicago)

[Chameleon](https://www.chameleoncloud.org/)
- Provides a testbed for exploring a range of problems in computer science (software development, kernel support for virtualization, etc.).
- ''Come for the hardware, stay for the services''. Fancy hardware that computer scientists love.
- Requirements for experimental workflow: 
    - discover resources 
    - allocate resources
    - configure and interact
    - monitor
- One of the goals of Chameleon: lower the cost of repeatable research
    - History of work
- Repeatability in Chameleon:
    - testbed versioning
    - application management
    - Every change in testbed is a recorded event
- Experiment Precis
    - Open stack services, instance monitoring, infrastructure monitoring and user events are stored and shareable. Jupyter notebooks could also be made.
- Active Papers
    - Moving beyond classic papers by improving scientific storytelling 
    - One way to do this by making papers interactive: Videos of active figures, links to citations and online discussions, live experiments.
    - Jupyter notebooks are the best example today for active papers.
    - Connecting Jupyter and Chameleon, you can allow interested readers/users to not just read your work, but play with it, using the resources of Chameleon.
- [OpenStack](https://www.openstack.org/)

### Questions

- Are there usage limits?
- API?
- Rollback to old version of hardware??

## Techniques and guidelines for reporting reproducible and statistically sound result — Torsten Hoefler (ETH Zürich)

Reproducable performance is hard (impossible)

Performance is something every researcher has to keep in mind, not just data or computer scientists.

Functional reproducibility is relatively simple -- just release the code! But... gets more complex when you share parallel codes (and you have non-associative operations (floats)).

Reproducing performance results is really hard but should be done - hardware configurations change, ex: 9 years later all of the data fits into cache, scaling with cpu cores changes.

Interpretability: 'don't do bad science', do reasonable research.

When measuring performance, there are important questions with that are often answered with random values (what your colleagues/supervisors/field says).

'Twelve Ways to Fool the Masses When Giving Performance Results on Parallel Computers' David H. Bailey ([Paper](http://crd-legacy.lbl.gov/~dhbailey/dhbpapers/twelve-ways.pdf))

1. Provide the absolute baseline performance and description of the base case.
2. Specify the reason for only reporting subsets of standard benchmarks/applications or not using all system resources.
3. Use the arithmetic mean only for summarizing costs. Use the harmonic mean for summarizing rates.
4. Avoid summarizing ratios: summarize the costs or rates that the ratios base on instead. (Only if these are not available use the geometric mean for summarizing ratios).
5. Report correct confidence intervals of any nondeterministic measurements. Don't trust your average textbook! Pay attention to normality. 
6. Do not assume normality of collected data without diagnostic checking.
    - Can test for normality before calculating confidence intervals, or use non-parametric CI. Performance is not normal distributed - usually only gets slower. This is because there is a max possible speed, and conditions only slow down execution

8. Carefully investigate if measures of central tendency, such as mean or median are useful to report. Some problems, such as worst-case latency, may require other percentiles. EX: Quantile regression: make more complex statements.
    - Use confidence intervals to determine the minimal number of measurements.

9. Experimental design is also important for minimizing experiment time but at the same time maximizing results.
    - Factorial design is recommended
    - Many books/courses available to learn about this
10. For parallel time measurements, report all measurements.
11. Provide some intuition on what your results mean, relative to theoretical limits for example.
12. Plot as much information as possible
    - Ex: combine box and violin plots

Reference Torsten's paper for more information on his talk:
[' Scientific Benchmarking of Parallel Computing Systems'](https://htor.inf.ethz.ch/publications/img/hoefler-scientific-benchmarking.pdf)f

## Practical data management — Anna Krystalli (University of Sheffield)

[dataspice](https://github.com/ropenscilabs/dataspice) - way for researchers to create lightweight, basic and concise metadata files for their datasets.

metadata collected in csv files, fields based on schema.org, have some helper functions and shinyapps to extract and edit those files

[Anna's tutorial](https://github.com/annakrystalli/dataspice-tutorial)

If installation of the package does not work for you try:

```
On Ubuntu 14.04 or 16.04 you can use the PPA:
  sudo add-apt-repository -y ppa:opencpu/jq
  sudo apt-get update
  sudo apt-get install libjq-dev
On other sytems try installing:
 * deb: libjq-dev (Debian, Ubuntu 16.10 and up).
 * rpm: jq-devel (Fedora, EPEL)
 * csw: libjq_dev (Solaris)
 * brew: jq (OSX)
```
### `dataspice` workflow

![data spice workflow](https://github.com/ropenscilabs/dataspice/raw/master/man/figures/dataspice_workflow.png)

<br>

# Wednesday

[back to top](#rcs18---notes)

## Publishing and maintaining open data — Bastian Greshake Tzovaras (OpenSNP, OpenHumans)

Slides are at: https://figshare.com/articles/Sharing_Data_Why_How_When_/7076708 

Move from reproducibility (same data & methods) to generalizibility (different data & methods) 

Way to do this: publish data. However, many don't, or don't provide it even when they said they would when asked.

Data should be FAIR. Tons of options for data repositories, choosing one dependents on data types, data size and academic field (check out F1000Research for guidelines especially for biosciences).

If you don't find a repository that fits, then maybe make your own!

But what data license to pick? So much confusion! Check out [reusabledata.org](http://reusabledata.org/)

Choose the most open license possible for you (CC0) -> as open as possible and as closed as necessary

How not to publish data... check out OkCupid controversy with 70000 users having their info uploaded to a data repository. [reddit link](https://www.reddit.com/r/datasets/comments/4ikzsu/osf_the_okcupid_dataset_a_very_large_public/)

Publish data but require that users read documentation and agree to terms. Ex for biomedical data sets: [Synapse](https://www.synapse.org/)

Participant-centered research: involve the participants in the research process, because they can be interested and offer feedback.

Quote (slightly reworded): "Why not put your genome data on github, it is code after all" :) 

[openSNP](https://opensnp.org/): completely open data (CC0), open source, crowd funded/sourced. ~7,000 users so far. Individuals and research groups have taken advantage of the datasets.

Cool usecases: 
- [Beginners Guide to Genetics Hacking](https://medium.com/@matthiasshap/the-beginner-s-guide-to-genetics-hacking-84d612b4235)
- OpenSNP Height Prediction (competition at epfl) Fun fact: winning team used expert knowledge and not machine learning. 

Downside: loss of control on data once you agree to share it on the platform.

[Open Humans](https://www.openhumans.org/): Platform for uploading data, with different privacy settings. Can have an account with customized anonymity and a bunch of different datasets / information about themselves. 
- Anyone can access (not only academics)
- Examples of data
    - pace data, apple health (Rumi?)
    - twitter
    - spotify
    - MRI images
    - google search data
    - ... (anything can be uploaded)
- few thousand users
- Can analyze your own data at Open Humans with Jupyter notebook and share your analysis with others to run on their own data (Juno's Exploratory, connected to Jupyter notebook).
    - Great way to send your codes/analysis but not your data directly.

Real example of using Open Humans:

Diabetes open hardware, because of 50% lifetime chance of dying in your sleep due to low blood sugar (pretty sure), created an artificial pancreas. Glucose blood monitor controls an insulin pump, regulating glucose level.  

Summary
- generalizable findings rely on sharing data
- plenty of places to share data
- share data with a license allowing remixing and reusing but sharing human data can be tricky

### Questions
How to get data on human-to-human interactions, such as geo-tagged facebook data? 
- tricky to know what is right or wrong when dealing with humans and their data in general. Just because it is doesn't mean that it is okay or if people will feel okay with that use of their data. Doing an ethical review before starting your project could help.
How much expertise in terms of coding do you need to use OpenHumans? 
- One can just press the play button of the jupyter notebook provided that there are no errors
- Depends on what comunity builds, some app for directly plotting your twitter history for example requires no coding at all. 
- otherwise it is currently not suited for people without programming experience. 

How big and problematic is the bias in terms of who is able / willing to use OpenHumans
- white humans have their genomes tested in academia mostly, or psychology students only study psychology students -> creates a huge bias anyways
- OpenHumans does not solve this bias problem in that sense, but is not worse either

Artificial pancreas: what is the liability situation here? What it something goes wrong?
- The researcher should always try to make their work as safe as possible, but it's going to be hard to stop anything going wrong. Sometimes you can't stop people from doing unreasonable things (stupid people :)
What is the growth rate of data being published? 
- slightly superlinear but not exponential
- it is getting better and better since people actually start having access to more of their personal data. 

Does the person wanting to share the data need to do a good job in prepping the data to share?
- Of course that's nice but many potential donors don't document their data properly, purely from not knowing any better. Also humans are unique and everyone documents themselves in differently. It's hard for researchers to prep donors to give data in a certain way (reproducibly).

## Tools for reproducibility in Statistics and Machine Learning — Heidi Seibold (LMU Munich)

Slides: https://goo.gl/sJqBNB
Video: https://youtu.be/JP1m8TkaJHY

Open versus reproducible science <-> altruistic versus extremely well-organized scientists (not necessarily an overlap!)

Typical steps in a project (check out presentation for mind map):

- data preparation
    - tool: RMarkdown, similar to Jupyter notebooks
- analysis preparation (think about what you want to do)
    - tools: LaTeX (pick statistical tests etc.), [OSF](https://osf.io/) to publish the plan
- analysis (do it)
- presentation
    - write up results
    - put preprint up 
    - update OSF publication (?) 

### tools overview

[Knitr software](https://www.r-project.org/nosvn/pandoc/knitr.html) - combines R and latex for generating reports
[Overleaf software](https://www.overleaf.com/) - Online LaTeX/rich text writing and publishing tool

I add this for python / c++ users: 
- Roxygen: Doxygen (C), sphynx (python), readthedocs (python)
- Rmarkdown/Knitr: Jupyter notebooks (python)

### make 

[Make software](https://www.gnu.org/software/make/) - help automate processing in project
(please some make expert check below)
- specify dependencies for target:
    - target: dependency1 dependency2 ...
        command_to_generate_target
- run "make target" or "make all" and it will only rerun command_to_generate_target if any of the dependencies have been changed

### Online Presence

- uni website
- twitter
- blog
- ORCID
- [Impactstory](http://impactstory.org/)

### OpenML
[link](https://www.openml.org/)

- data
- task (question about dataset such as delay of buses in Zurich)
- flows (algorithms)
- results (which flow gave which result on which data)

### Questions

Do you consider Linked-In a good place for an online presence?
- She doesn't use but suggests could be useful if leaving your academic bubble.

Tryout - how to order the potential mess (100s of Jupyter notebooks)
- Use some naming conventions and eventually delete unneeded code (it's saved on version control so it's never really gone)

Online presence: best place for impact?
- Twitter, connect to people you wouldn't really know about otherwise. Can share thoughts with people in a small and controlled way.
- Blog is cool but requires more work.
- Conferences are also useful for meeting people.

At what point did you figure out your process flow?
- In progress for her to learn as well. Lots of trial and error and maybe later after you find the 'right way' she may change again. She thinks it's important to be able to explain why you use a tool or process or change to something else.
    - Anna feedback: have internal reports that you can share for discussion, kind of like meeting notes

## How to write a ~~perfect~~ *pretty good* reproducible paper (Workshop) — Christie Bahlai (Kent State University) & Anna Krystalli (University of Sheffield) 

Slides: https://docs.google.com/presentation/d/1MYetj9Ytd7rrGfbgIQoSLkwukN9qf-oqhuvpY3eoCIA/edit?usp=sharing

Paper: http://rsos.royalsocietypublishing.org/content/3/12/160712

Code repo: https://github.com/ReproducibleQM/rebugged

Data: https://figshare.com/articles/LTER_Mecoptera_data/3569313

# Thursday

[back to top](#rcs18---notes)

## Team 1

Topic: Do people only retweet tweets respecting the same ideoligy? 

12 topics, in particular for more political topics, the people are more likely to retweet same ideology

Workflow:
Public and. Private dimension

Data matching and validation are not public, possibly because of privacy issues

Pros and Cons of github:
- github is actually a fork, and it is 2 commits behind. Could be missing important information?  
- no LICENSE file
- no releases, tags
- no issue tracking, no Contributing.md for rules and engagement, how to get involved. 
- README fairly good. 
    - description of files and link between them
    - link to data
    - no instructions for how to run the code
    - no mock datasets to see the scripts in action. 
- code structure fairly clear, and good connection with pipeline
- dependencies: good attempt, but versions are missing. 
- no continuous integration, no automated tests
- data:
    - Harvard repository, no need to sign in 
    - CC0 license
    - even has code under CC0 license 
    - everything in standard formats
    - DOI
    - bit hard to track versions between ?
- Main version behind paywall, but preprints available. 
- De-anonymization:
    - many tweets have actually been removed 
    - out of 500 randomly selected tweets only 20% were left! 
    - X-rate-limit-reset
- Code very buggy! Didn't build, gave syntax (?) errors.

Conclusions

- Trade off between privacy and reproducibility
- more than 200 citations but only 4 forks

Suggestions

- Docker for dependencies
- MyBinder to play around with code
- version code and data more consistently

## Team 2

Stone artefacts and other archeological components from Madjedbebe

all raw data and source available, reproducible in one click.
- dockerfile available
- even creates nice supplementary material by 1 click (knit)
- one script, but also function.r file with all functions. 
    - all functions well documented,
    - functions not really reusable
- only flaw: paper on Elsevier, not publicly available. 


## Team 3

Tsunamis and how it effects the flooding in areas around it. How Tsunami is more destructive in regions of high tide than in regions of low tide.

Part of a bigger project. This paper is only about "pattern method" (?), other components such as GeoClaw for simulating Tsunamis are more developed and reliable. 

3 models used, hazard maps created. Can create public panic? 

- Test dataset accessible (Zenodo) but not all data that was used in the study since sensitive. 
- Code available
- Everything generating fine.
- README very complicated
- No version information or dependencies given

Potential improvements

- specify versions
- have a little bash script to do all the necesary steps automatically
- create docker file

## Team 4

Long-term nerual study of phenotyping on a single human (first author). 
Claims very good reproducibility. 

Theory
- Set up a virtual machine (VirtualBox, Vagrant, git)
- using vagrant up, start analysis process and go to local website to see results after roughly 2 hours

Practice
- wait for 5 hours to complete
- specify versions in vagrantfile
- had to change to previous Linux base image for R versions to be compatible 
- missing  R dependencies
- Local server: really nice interface, but hard to find what you are looking for.
    - a lot of data etc downloaded, good standard dat aformats
    - can explore the data 
    - one of the figures could be reproduced
    - very hard to understand what all the figures produced mean, many of them are not in paper. 
    - some plots cannot be generated because of errors
- Very little software documentation, short docstrings. 
- Software engineering: some tests, not up-to-date distribution. Mix of different languages, not very easy to navigate, in particular since it is not documented well. 
- Authors justify not having any description of what each function does, by providing a run_everything.py file. 
- Thanks to very good documentation of flask and networkx, it was easy to find required version. 

## Team 5

Teach a CNN to predict if data is worth saving and analyzing or not. 

- Software, data, paper availability: Gold open access, data CC0, software 3-clause BSD
- Data in repository for x-ray imaging (CXIDB).
- All Code on github, repo in same state since publication.
- Software:
    - README hard to find, not very informative
    - folder with neural network, slightly more informative README. Need to install dependencies
        - using CUDA 8 -> need to downgrade to that, and downgrade other dependencies accordingly, some of them not really available anymore. Dependecy mess
        - train, test scripts on one vs. multiple datasets, but can't reproduce any figures. 
        - *Deal with your dependencies, version them!* things break fast, ex 2 years and it's all changed
        - Modern languages (ex: python, R) often have a way of handling dependencies, in C/C++ land it's easier to make a docker or VM
        - Code is in an ok state

Reasons for using docker: 
- needs CUDA 8, which uses gcc5, which can mess up your whole system. Containerizing could save you from reinstalling/downgrading many packages on your computer. 
- 

## Team 6

Identify number and direction of sound sources using an array of calibrated microphones. In particular find out the angular resolution that can be reconstructed correctly. 

- Open access on arXiv
- Good setup description.
- Directions to other papers to understand fully the method. 
- Git link a little bit hidden.
- Very nice README file. 
    - binder failed
- python version for check_requirements.py missing (only mentioned in the end of the file)
- requirements.txt, versions are missing
- good download instructions, but needed to install wget function.
- make_all_figures.sh
    - helpful warning that it will take long.
    - did the short script instead 
    - finished without error, but actually there was a runtime error (figures not reproduced, simply copied from github).
        - package request was missing 
        - DejaVu font missing
- no documentation, but docstrings in code. Not easy to understand
- within 4 pages not enough space to actually understand the algorithm. 
 
## Team 7

Synthesise light field image (8x8 images) using 4 corner images. Done using 2 neural networks: one disparity estimation, one color prediction network.

- Automation: seems ok, both training and testing using pretrained network. 
- Exact figures cannot be reproduced
- All data available on the website. No DOI. 
- Software also available on website. README mentions two versions, available one probably the latest one, but not clear. 
- Testing was ok
- Training did not work because of MatConvNet dependency. 
- Could do the training on CPU only, but would probably take too long. 
- Only 2 parameters documented. 
- Everything under copyright, "personal use" only? 

