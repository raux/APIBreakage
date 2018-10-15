An Empirical Study on the Impact of Refactoring Activities on Evolving Client-Used APIs
------
**(Information and Software Technology Journal)**

[Link to Publication](https://arxiv.org/abs/1709.09474)

## Abstract
*Context:* Refactoring is recognized as an effective practice to maintain evolving software systems. For software libraries, we study how library developers refactor their Application Programming Interfaces (APIs), especially when it impacts client users by breaking an API of the library. 
*Objective:* Our work aims to understand how clients that use a library API are affected by refactoring activities. We target popular libraries that potentially impact more library client users. 
*Method:* We distinguish between library APIs based on their client-usage (refereed to as client-used APIs) in order to understand the extent to which API breakages relate to refactorings. Our tool-based approach allows for a large-scale study across eight libraries (i.e., totaling 183 consecutive versions) with around 900 clients projects.
*Results:* We find that library maintainers are less likely to break client-used API classes. Quantitatively, we find that refactoring activities break less than 37% of all client-used APIs. In a more qualitative analysis, we show two documented cases of where non-refactoring API breaking changes are motivated other maintenance issues (i.e., bug fix and new features) and involve more complex refactoring operations. 
*Conclusion:* Using our automated approach, we find that library developers are less likely to break APIs and tend to break client-used APIs when addressing these maintenance issues.

**Replication Package**
ReplicationPackage.rar (check repository)
jarBinaries.rar (taken from Maven)
Note that for all data, we first downloaded an offline copy of the original data before extraction.

**Mining Tools and Libraries:**

Breakage Extraction - We use the [japi-cmp](https://github.com/siom79/japicmp) tool as a library to implement breakage extraction.

Refactoring Extraction – [Ref-Finder](https://sites.google.com/site/reffindertool/) was used to extract the refactorings,

Client API Extraction – Combination of our [Pomwalker](https://github.com/raux/PomWalker) tool was used to identify relevant repositories, then we used the [JavaCompiler](https://docs.oracle.com/javase/7/docs/api/javax/tools/JavaCompiler.html) tool ( set to use JDK 1.6) to compile and extract classes. For building, we needed to re-create the build environment, thus the [jcabi](https://www.jcabi.com/) tool was used to resolve all transitive dependencies on the build path. We used the java asm library to extract out the fully qualified class names.
