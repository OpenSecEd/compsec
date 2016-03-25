A Course on Computer Security (compsec)
===============================================================================

This is an introductory course on computer security.  It's aim is to provide 
the student with an overview of the security required within a computer system.

It is part of the [Open Security Education][OpenSecEd] project and the 
maintainer is [Daniel Bosk][Maintainer].  The latest release can be found under 
[releases][Releases].  You can safely link directly to the PDFs found there.

[OpenSecEd]: https://github.com/OpenSecEd
[Maintainer]: https://github.com/dbosk
[Releases]: https://github.com/OpenSecEd/compsec/releases

This course consists of several learning modules that are linked in this repo.  
However, all required PDFs can be found under [releases][Releases]


File Structure and Building
===============================================================================

The main document of this repo is the study guide, for which the source code 
can be found in `studyguide`.  The other directories are submodules needed to 
build the study guide.

The study guide ties together a set of learning modules.  Each learning module 
contains lectures, assignments etc.  Currently the course comprises the 
following topics:

 - Foundations of Security (`foundations`)
 - Information Theory (`infotheory`)
 - Cryptography (`appliedcrypto`)
 - Identification and Authentication (`auth`)
 - Security Usability (`usability`)
 - Access Control (`ac`)
 - Reference Monitors (`refmon`)
 - Secure Protocols (`fverif`)
 - Accountability and Non-Repudiation (`accountability`)
 - Software Security (`software`)
 - Trusted Computing (`trustcomp`)
 - Side-Channels (`sidechannels`)

These topics are examined using the following assignments.  The assignments 
prefixed with L are individual laboratory assignments, H are hackathon labs 
(done full-day in class), prefixed with M are memos, S for seminars.

 - L0: Brute Forcing (`appliedcrypto/spuriouslab`)
 - L1: Password Cracking and Social Engineering (`passwd/pwdguess`)
 - S2: Password Policies (`passwd/pwdpolicies`)
 - L3: Privacy of Communication (`pricomlab`)
 - L4: Tools of the Trade (`toolslab`)
 - H5: Digital Rights Management (`drmlab`)
 - H6: Smashing the Stack (`stacksmashlab`)
 - S7: The Computer Engineer's Code of Ethics (`ethics/profession`)


Building
-------------------------------------------------------------------------------

*To build* the PDFs, after cloning the repository you must clone its required 
submodules:
```shell
$ git submodule update --recursive --init
```
Then you can go into the directory of the desired document and run `make`.
If you run `make` in the root directory you will recursively transcend the 
directory hierarchy and build everything included in the course.

*To contribute*, please [fork the repository][ForkARepo], make your changes, 
commit them and then create a [pull request][PullRequest] in the original 
repository.

[ForkARepo]: https://help.github.com/articles/fork-a-repo/
[PullRequest]: https://help.github.com/articles/using-pull-requests/File structure

