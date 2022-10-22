# Original Java Specification Request (JSR)

- [Original Java Specification Request (JSR)](#original-java-specification-request-jsr)
  - [Section 1. Identification](#section-1-identification)
  - [Section 2: Request](#section-2-request)
    - [Please describe the proposed Specification:](#please-describe-the-proposed-specification)
    - [What is the target Java platform? (i.e., desktop, server, personal, embedded, card, etc.)](#what-is-the-target-java-platform-ie-desktop-server-personal-embedded-card-etc)
    - [The Executive Committees would like to ensure JSR submitters think about how their proposed technology relates to all of the Java platform editions. Please provide details here for which platform editions are being targeted by this JSR, and how this JSR has considered the relationship with the other platform editions.](#the-executive-committees-would-like-to-ensure-jsr-submitters-think-about-how-their-proposed-technology-relates-to-all-of-the-java-platform-editions-please-provide-details-here-for-which-platform-editions-are-being-targeted-by-this-jsr-and-how-this-jsr-has-considered-the-relationship-with-the-other-platform-editions)
    - [Should this JSR be voted on by both Executive Committees?](#should-this-jsr-be-voted-on-by-both-executive-committees)
    - [What need of the Java community will be addressed by the proposed specification?](#what-need-of-the-java-community-will-be-addressed-by-the-proposed-specification)
    - [Why isn't this need met by existing specifications?](#why-isnt-this-need-met-by-existing-specifications)
    - [Please give a short description of the underlying technology or technologies](#please-give-a-short-description-of-the-underlying-technology-or-technologies)
    - [Is there a proposed package name for the API Specification? (i.e., javapi.something, org.something, etc.)](#is-there-a-proposed-package-name-for-the-api-specification-ie-javapisomething-orgsomething-etc)
    - [Does the proposed specification have any dependencies on specific operating systems, CPUs, or I/O devices that you know of?](#does-the-proposed-specification-have-any-dependencies-on-specific-operating-systems-cpus-or-io-devices-that-you-know-of)
    - [Are there any security issues that cannot be addressed by the current security model](#are-there-any-security-issues-that-cannot-be-addressed-by-the-current-security-model)
    - [Are there any internationalization or localization issues?](#are-there-any-internationalization-or-localization-issues)
    - [Are there any existing specifications that might be rendered obsolete, deprecated, or in need of revision as a result of this work?](#are-there-any-existing-specifications-that-might-be-rendered-obsolete-deprecated-or-in-need-of-revision-as-a-result-of-this-work)
    - [Please describe the anticipated schedule for the development of this specification.](#please-describe-the-anticipated-schedule-for-the-development-of-this-specification)
  - [Section 3: Contributions](#section-3-contributions)
    - [Please list any existing documents, specifications, or implementations that describe the technology. Please include links to the documents if they are publicly available.](#please-list-any-existing-documents-specifications-or-implementations-that-describe-the-technology-please-include-links-to-the-documents-if-they-are-publicly-available)
    - [Explanation of how these items might be used as a starting point for the work.](#explanation-of-how-these-items-might-be-used-as-a-starting-point-for-the-work)

## Section 1. Identification

* Submitting Member: 
  * 提交成员（JUG成员）
* Name of Contact Person:
  * 联系人
* E-Mail Address:
  * 联系邮件地址
* Telephone Number: 
  * 联系电话
* Fax Number:
  * 传真电话
* Specification Lead:
  * 申明主导人
* E-Mail Address:
  * 主导人联系邮件地址
* Telephone Number: 
  * 主导人联系电话
* Fax Number:
  * 主导人传真电话
* Initial Expert Group Membership: 
  * 初始主导的专家成员组（JUG成员）
* Supporting this JSR:
  * 支持的专家成员组（JUG成员）


## Section 2: Request

### Please describe the proposed Specification:

描述该诉求

Nowadays, users of the Java Programming language need to be able to facing the problems below.

Firstly, the resouce of thread pools is depending on the machine(or we may say container). [JSR133](https://www.jcp.org/en/jsr/detail?id=133) has some description.

Secondly, users of the Java Programming language facing the problem of thread, who were required higher ability.

Thirdly, depending the differences of the situations. Some of them will require the pyramidal thread pools to facing(or may say solving) the domain business. However, making thread run faster that would be the next requirement. Like: solving stacktrace, organize priority and waking all threads using stacktrace to running the thread.

当今环境下对线程的使用管理和构建的痛点，如下：
* 线程池的大小和实际服务器的资源情况相关 JSR133有相关描述
* 遇到线程问题时，解决者的综合素养能力要求较高
* 根据不同的业务实际场景，会有金字塔型的线程池管理编码诉求，此时可以有优化或有效进行线程的统筹管理，但是实现方式其实较为通用：处理依赖链路，进行优先级规划，或以全局视角直接通过唤醒所有线程，根据链路进行运行线程



### What is the target Java platform? (i.e., desktop, server, personal, embedded, card, etc.)

实现方案会使用推广的平台

All plateform

全平台

### The Executive Committees would like to ensure JSR submitters think about how their proposed technology relates to all of the Java platform editions. Please provide details here for which platform editions are being targeted by this JSR, and how this JSR has considered the relationship with the other platform editions.

执行委员会对JSR提交者的技术目的想法在Java平台版本做确认。请提供相关平台版本关联或者指向该JSR的详情，以及考量该JSR与各个平台版本的关系



### Should this JSR be voted on by both Executive Committees?

该JSR是否需要执行委员进行投票

No, the achievement of this JSR has been submitted at the master.

不需要，该JSR的实现已被提交至master分支

### What need of the Java community will be addressed by the proposed specification?

希望Java社区对该声明放置的位置

Users of the Java Programming language need to be able to write reliable multithreaded software and understand which thread communication idioms are leagal.

用java进行编程，并希望编写可靠的多线程软件以及理解合理的多线程间的信息沟通方式

The Java community will benefit from the additional API and usability improvements that will ease portability of multithreaded software.

Java社区会因此受益，且提高了对多线程软件的移植性。

### Why isn't this need met by existing specifications?

为什么已有的标准方案中并没有相关描述




### Please give a short description of the underlying technology or technologies

请简短描述该技术

Please see 2.1 above.


### Is there a proposed package name for the API Specification? (i.e., javapi.something, org.something, etc.)

该相关代码声明的放置包位置

java.lang


### Does the proposed specification have any dependencies on specific operating systems, CPUs, or I/O devices that you know of?

是否依赖特定系统、CPU、输入输出设备

no

### Are there any security issues that cannot be addressed by the current security model

是否涉及相关安全/权限模型

no


### Are there any internationalization or localization issues?

是否有任何全球或本地的issue关联

* [#8289284](https://github.com/openjdk/jdk/pull/9308)


### Are there any existing specifications that might be rendered obsolete, deprecated, or in need of revision as a result of this work?

是否有任何相关的申明与此关联，或废弃，或以来于此JSR的成果

This JSR has some infomations which were connected with JSR121 and JSR133.

本JSR有部分信息与JSR121和JSR133相关联


### Please describe the anticipated schedule for the development of this specification.

请描述任何计划或开发内容关于此JSR




## Section 3: Contributions
贡献章节

### Please list any existing documents, specifications, or implementations that describe the technology. Please include links to the documents if they are publicly available.

请列举相关已存在的文档、申明或实现该描述的技术

* [JSR121](https://www.jcp.org/en/jsr/detail?id=121)
* [JSR133](https://www.jcp.org/en/jsr/detail?id=133)
* [VirtualThread.java](https://github.com/openjdk/jdk/blob/master/src/java.base/share/classes/java/lang/VirtualThread.java)

### Explanation of how these items might be used as a starting point for the work.

请说明为何这些点被适合被使用于成果中
