In this section I shall compare several existing OSS wiki systems, that by design and feature set most strongly resemble traits described in previous chapter.

Since the requirements are too restrictive, I shall examine systems using Git VCS for data storage, regardless of how they satisfy remaining demands.

I shall discuss the remaining requirements individually with each suspect and describe where it excels and where it inferior.
The remaining desired features, apart from Git VCS in back-end are:

* **User access control**
    * How powerful is it?
    * What security scopes are available? Protected branches, paths etc.?
    * Is the configuration version controlled?

* **Direct repository access**
    * Is there direct access via Git CLI available?
    * How is authentication handled with web login and (presumably) SSH key pairing?

* **Document format**
    * What languages are supported?
    * Is Markdown or Asciidoc supported?
    * Is it possible to modularly add new LMLs?
    * What features are supported by the editor?

* **Branching model**
    * Is Git branching model available in wiki; e.g. can multiple branches be maintained independently?

* **UI**
    * How is UI handled for common screens like file index, page detail and page edit?^[This might be interesting, to observe how UI is affected by the fact that system runs on VCS Git. UI might shift slightly from "document hub" (known from common wiki software like MediaWiki[@mediawiki] or DokuWiki[@dokuwiki]) to more broad perspective of generic repository browser.]


I have defined the acceptance and quality criteria.
Based on former I shall inspect several popular systems that either run on VCS Git or can be configured to use it as a primary content repository.
The systems Wiki.js, Gollum, Gitit and Ikiwiki, complete the list of all major OSS projects I found in my research, which are backed, or can be in that matter, by VCS Git.

Some items on the list are not repository hosting services per se, for instance Gollum, which is only a WUI for managing Git repository.
Since the number of the project passing the acceptance criterion is thin as it is, I decided to include Gollum as well, mainly for its UI research value.

The list could be potentially extended if plug-ins or extensions were considered.
This way I could include popular platforms such as MediaWiki or DokuWiki.
I have decided to exclude extensions and consider only platforms which are designed to work with a VCS repository, for there is a greater chance to learn more about implementation and UI specifics designed for systems backed by Git.