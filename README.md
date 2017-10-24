![bitcoinj](bitcoinjlogo.png)

# bitcoinj
By [Lucie JORDAN](https://github.com/LucieJ95), [Joana MARTINI](https://github.com/joanamartini), [Mamadou Diambar NDOUR](https://github.com/mndour), [Clément OZOUF](https://github.com/cozouf) and [Md. Wali UL ALAM](https://github.com/walicse15)


## সারাংশ

বিটকয়েন একটি জাভা লাইব্রেরি যা বিটকয়েন অর্থের জন্য ডিজিটাল ওয়ালেজ তৈরির উপর জোর দেয়। এই ডকুমেন্টেশনটি তার সফ্টওয়্যার আর্কিটেকচারের বিভিন্ন দিক সহ একটি বাহ্যিক দৃষ্টিভঙ্গি প্রদান করে। প্রথমত, বিটকয়েনের ব্যবহার এবং অবদানের সাথে জড়িত ব্যক্তিদের একটি বিশ্লেষণ করা হয়, প্রতিটি গ্রুপের ভূমিকা বর্ণনা করে। উপরন্তু আমরা লাইব্রেরি বাহ্যত সত্ত্বা উপর বিস্তৃত। পরবর্তী, আমরা বিটকয়েনের মডিউলের কাঠামোটি বিশ্লেষণ করি না, তবে জিথাব রিপোজিটরিতে ডিরেক্টরিগুলির উন্নয়ন, পরীক্ষা এবং ডিরেক্টরিগুলির শক্তিশালী মানদণ্ডও। পরিশেষে, সিস্টেমের একটি গভীর বিশ্লেষণটি ব্যবহার করা হয় যাতে বিটকয়েনের একটি ভাল মানের বৈশিষ্ট্য হিসাবে ব্যবহার করা যায়। আমরা ডকুমেন্টেশন শেষ করে আমাদের সব ফলাফলের একটি সংক্ষিপ্তসার।


## সুচিপত্র
* [ভূমিকা](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#introduction)
* [স্টেকহোল্ডার বিশ্লেষণ](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#stakeholders-analysis)
  * [পাওয়ার সুদ গ্রিড](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#power-interest-grid)
  * [জিআইটি রিপোজিটরি বিশ্লেষণ](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#analysis-of-git-repository)
* [কনটেক্সট ভিউ](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#context-view)
  * [সিস্টেম সুযোগ এবং দায়িত্ব](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#system-scope-and-responsibilities)
  * [বাহ্যিক সত্ত্বা এবং ইন্টারফেস](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#external-entities-and-interfaces)
* [উন্নয়ন দৃশ্য](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#development-view)
  * [মডিউল সংগঠন](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#module-organization)
  * [কোড লাইন সংগঠন](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#codeline-organization)
  * [নকশা মানায়ন](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#standardization-of-design)
  * [পরীক্ষার মানদণ্ড](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#standardization-of-testing)
* [একটি গুণ অ্যাট্রিবিউট বিশ্লেষণ](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#analysis-of-a-quality-attribute)
* [উপসংহার](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#conclusion)
* [তথ্যসূত্র](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references)

## Introduction

শতাব্দী এবং শতাব্দী ধরে, সমাজকে অর্থের বিনিময়ে প্রধান উপায় হিসাবে ট্রেড করা হয়। আজকাল, অর্থ মহান গুরুত্ব। প্রকৃতপক্ষে, এটি জীবনযাত্রার পথ সহজ করে তোলে, উদাহরণস্বরূপ যদি আপনি আপনার সান্ত্বনাটি উন্নত করতে চান বা সাংস্কৃতিক কার্যক্রমগুলি অ্যাক্সেস করতে চান। এর মানে হল যে আপনি সামাজিক সাফল্য অর্জন করেছেন কিন্তু টাকা আমাদের জীবনে একটি বিশিষ্ট স্থান নিতে প্রদর্শিত যা একমাত্র উপাদান নয়। উদ্ভাবনী প্রযুক্তির কয়েক দশক ধরে অগ্রগতি হয়েছে, এবং একটি শতকেরও কম সময়ে, আমরা একটি সমাজ তৈরি করেছি যেখানে প্রযুক্তি আমাদের দৈনন্দিন জীবনের সর্বব্যাপী।

২008 সালে, সতোশি নাকামতো তার বিটকয়েন প্রকল্পটি ঘোষণা করে, যা প্রযুক্তি এবং অর্থের সাথে যুক্ত: "বিটকয়েন" একটি ডিজিটাল মুদ্রা। মূলত, এই ভার্চুয়াল টাকা আপনার ডিজিটাল ওয়ালেট মধ্যে রয়েছে, আপনার কম্পিউটার বা আপনার মোবাইল ডিভাইস থেকে অ্যাক্সেস যাতে আপনি এটি ব্যবহার করতে পারেন। নির্মাতা গণিতশাস্ত্রে তার প্রকল্পটি ভিত্তি করে এবং এই মুদ্রাটি কোনও কর্তৃপক্ষের দ্বারা নিয়ন্ত্রিত হতে চায় না: এজন্যেই এটি কোনো প্রতিষ্ঠান থেকে স্বাধীন, এবং সেইজন্য, লেনদেনের ফি কম।

এটি ২009 সালে একটি মুক্ত উত্স হিসাবে সফ্টওয়্যারের প্রথম সংস্করণ প্রকাশ করা হয়। মূল প্রশ্ন হচ্ছে বিটকয়েন কীভাবে কাজ করে?

এটি ব্লকচেইনের নীতির উপর ভিত্তি করে। ব্লককেন একটি বিশাল ডাটাবেস গঠন করে, ব্লকগুলিতে বিভক্ত হয় যা নির্দিষ্ট সময়ে তৈরি করা হয় এবং এর ফলে তাদের নিজস্ব টাইমস্ট্যাম্প থাকে। একটি ব্লক এটি তৈরি করা সময়ের মধ্যে তথ্য যোগ করা হয়েছে: এই তথ্য এই সময়ের মধ্যে ঘটেছে যা লেনদেন সম্পর্কে তথ্য ধারণ করে। সময় শেষ হলে ব্লকব্লাইনটি ব্লককে যুক্ত করার সময় ব্লক হল টাইমস্ট্যাম্পড। দুইটি ব্লক সংযুক্ত করা হয়, যার মানে আপনি একটি ব্লক অ্যাক্সেস করতে পারবেন না যদি আপনি আগের এক অ্যাক্সেস না করে থাকেন।

![blockchain](blockchain_principle.png)

*Figure 1: Blockchain principle. (Image source [[1]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references) (the text has been translated in order to make the image understandable))*

মূলত, Bitcoin কোন সেন্ট্রাল সার্ভার ব্যবহৃত হয় একটি উপায় কাজ করে। পরিবর্তে, কিছু ব্যবহারকারী ডিভাইস ডেটা সংরক্ষণ করতে ব্যবহার করা হয়। এটি একটি "পিয়ার-টু-পিয়ার" নেটওয়ার্ক, যার মানে ফাইলগুলি কম্পিউটার থেকে কম্পিউটারে বিনিময় করা যায়। এই ডিভাইস মানুষ, মালিকদের মালিকানাধীন, যারা এই নেটওয়ার্ক অংশ হওয়ার জন্য জিজ্ঞাসা।

একটি লেনদেন বৈধ করার জন্য, খনির একটি গাণিতিক সমস্যা সমাধানের সঙ্গে PoW হিসাবে পরিচিত "কাজের প্রমাণ" এগিয়ে যাওয়ার আছে। যদি একটি ব্লকের মালিক এই সমস্যার সমাধান করেন, তবে এই ব্লকটি সিঙ্ক্রোনাইজার নামে নামকরণ করা হয় এবং শিকলটির সমস্ত ব্লকগুলিকে সিঙ্ক্রোনাইজ করা হয়।

BitcoinJ সম্পর্কে, এটি একটি জাভা / অ্যান্ড্রয়েড লাইব্রেরি যা Bitcoin টাকা জন্য ডিজিটাল wallets নির্মাণের উপর দৃষ্টি নিবদ্ধ করে। এই লাইব্রেরিটি এই ডিজিটাল ওয়ালেটগুলি উপলব্ধি করার জন্য অনেকগুলি বৈশিষ্ট্য রয়েছে। উদাহরণস্বরূপ, এটি ডেভেলপারদের তাদের নিজস্ব অ্যাপ্লিকেশনে একীভূত করতে সক্ষম করে, সরাসরি সরাসরি বিটকয়েনের নোডগুলি সংযুক্ত করতে এবং পাবলিক এবং প্রাইভেট কীগুলি সঞ্চয় করতে এবং শেষ লেনদেনগুলি সঞ্চয় করতে পারে। 


## স্টেকহোল্ডার বিশ্লেষণ

এই বিভাগে, আমরা স্টেকহোল্ডারদের বিশ্লেষণ এবং চিহ্নিত করি, যারা মূলত এমন ব্যক্তি যারা কোম্পানীর স্বার্থ আছে। আমরা তাদের প্রয়োজনীয়তা এবং বিটকয়েন লাইব্রেরি থেকে প্রয়োজনীয়তা নিয়ে আলোচনা করি। তারপর, এই প্রকল্প প্রভাবিত যে বিভিন্ন স্টেকহোল্ডারের শ্রেণীবিভাগ, Rozanski এবং উডস তাদের বই আলোচনা হিসাবে উপলব্ধ করা হয় [[7]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references). 

*Table 1: Stakeholders of bitcoinj*

| Class of stakeholders        | Description                | BitcoinJ stakeholder                                       |
| ---------------------------- |:---------------------------|:-----------------------------------------------------------|
| Acquirers                    | Oversee the procurement of the system or product. | Bitcoinj is mainly a library for Bitcoin implementing the Bitcoin Protocol. This product is built by Mike Hearn who was then a google employee. Mike Hearn is considered to be the acquire as he is the founder of bitcoinj. [[8]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references) |
| Communicators                | Explain the system to other stakeholders via its documentation and training materials.|On the official website of bitcoinj, there are lots of materials written by communicators which explain to other stakeholders how to use this project. There are also some tutorials which can be used in order to learn how to use this library, and a community where you can find answers of different questions and issues.                                                 |
| Contributors                 | Help in developing new features as well as they help in bug fixing issues. | In the open source application, contributors have a vital role to play, as well as the core developers, because most of time, core developers are busy with solving issues and they got less time to develop new features. After analyzing the commits and pull requests we can see some contributors who are contributing in this project, in particular <a href="https://github.com/TheBlueMatt">Matt Corallo</a> and <a href="https://github.com/devrandom">Dev Random. |
| Developers                   | Construct and deploy the system from specifications (or lead the teams that do this).   |This group has a large influence in this project, because they do not only they write the core code of bitcoinj: they also write the set of rules used in the Bitcoin protocol. They write the rule book. Since almost everybody does use their code and does follow their rules and practice, you could argue that they have the power. There are two people who compose the core team of developers: 1.  Mike Hearn 2. Andreas Schildbach and other contributors/GitHub users if their pull requests get accepted by the core team. | 
| Suppliers                   | Build and/or supply the hardware, software, or infrastructure on which the system will run. | Since bitcoinj library is implemented using Java 6, Java is the main supplier of this project. Java 6 is used for the core modules and Java 8 for others. The second supplier we can analyze from the project is Maven3+, which is the project management tool used for project building, documentation and dependencies. Google protocol buffer is the third supplier, as it helps serialization and hardware communication. And the last, but not least, Github itself, because it is providing the hosting of version control system. |
| Testers                     | Test the system to ensure that it is suitable for use.   | Developers write tests when implementing new functionalities. Bitcoinj uses different test modules that are used during the process of testing. We will later explain shortly these modules, in the stardardization of testing. |                                                                                                
| Users                     | Define the system’s functionality and ultimately make use of it.   | Bitcoinj is used by people, particularly those who want an easier way to do their transactions with bitcoin by creating their own digital wallet. These users represent an important part of this project, because they are at the same time contributors of this system’s improvement. Thereby, you can see this in the open source file on Github, where many bugs or issues are reported and many pull requests from different users are accepted by the admins. |

### পাওয়ার সুদ গ্রিড 

প্রথম ধাপ সম্পন্ন করার পরে, আমরা এই প্রকল্প দ্বারা প্রভাবিত বা প্রভাবিত যে সবচেয়ে গুরুত্বপূর্ণ স্টেকহোল্ডারদের আবিষ্কৃত এবং ব্যাখ্যা, আমরা তাদের শক্তি এবং সুদ দ্বারা শ্রেণীভুক্ত করা হবে, শক্তি-স্বার্থ গ্রীড ব্যবহার করে।

মূল অংশীদার যারা ক্ষমতা এবং সুদ আছে অবশ্যই হয় মূল ডেভেলপার দল, অবদানকারী এবং এছাড়াও অর্জনকারী, বিটকয়েনের প্রতিষ্ঠাতা।

২ য় ধাপে দেখানো দ্বিতীয় গ্রুপ, নিম্ন শক্তি এবং নিম্ন সুদ সহ স্টেকহোল্ডারগুলিও মেন, বিটকয়েন, জিথাব, জাভা এবং গুগল প্রোটোকল বাফার। তারা কম শক্তি বলে বিবেচিত হয় কারণ তারা সহজেই অন্য IDE বা অন্য প্রোগ্রামিং ভাষার দ্বারা প্রতিস্থাপিত হতে পারে এবং সাধারণভাবে তাদের বিটকয়েনে কোন আগ্রহ নেই।

স্টেকহোল্ডারের শেষ গ্রুপ যে উচ্চ সুদ আছে, কিন্তু কম শক্তি ব্যবহারকারীদের হয়। ব্যবহারকারীদের কেবলমাত্র কয়েকজন এই প্রকল্পে অংশগ্রহণকারী হতে পারে, যদি তাদের পুল অনুরোধ গৃহীত হয়, তবে এই পণ্যটিতে তাদের উচ্চ আগ্রহ রয়েছে, কারণ তারা এর কার্যকারিতার ওপর নির্ভর করে। 


![PowerInterestGrid](PowerInterestGrid.jpg)

*Figure 2: Power - Interest grid*
                                                                                                             

### জিআইটি রিপোজিটরি বিশ্লেষণ                                                    

বিটকয়েনের জিআইপি রিপোজিটরির বিশ্লেষণের উপর ভিত্তি করে, প্রকল্পটিতে অবদান কম এবং প্রকল্পটির সর্বশেষ ধাপের প্রায় 13 দিন আগে সমস্যাগুলির মত কয়েকটি অংশ পরীক্ষা করে, অনুরোধগুলি এবং সেগুলি আদায় করে, এটি প্রকল্পে সবচেয়ে বেশি অবদানকারী কে অনুমান করা সহজ।

*ছক 2: জিআইটি রিপোজিটরি বিশ্লেষণ*

| বিবরণ           | ফল           | 
|:--------------------- |:-----------------| 
| ওপেন টান অনুরোধ    | 21               | 
| Close pull requests   | 639              | 
| Contributors          | 84               |  

স্টেকহোল্ডার বিশ্লেষণের মতে, আমরা লক্ষ্য করতে পারি যে, এক অবদানকারী যিনি পুল অনুরোধ গ্রহণ করেন, সমস্ত সমস্যা এবং ডিক্সড চেক করেন যা অনুরোধগুলিকে মার্জ করা উচিত, তারপর কিছু সাধারণ ডেভেলপাররা এই ওপেন সোর্স প্রোজেক্টে খুব কাছ থেকে অবদান রাখছেন বৈশিষ্ট্য আপডেট এবং বাগ ফিক্সিং বিষয় প্রথম সময়।


## Context view

প্রসঙ্গ ভিউ সম্পর্ক, নির্ভরশীলতা, এবং বিটকয়েন এর পরিবেশের (মানুষ, সিস্টেমগুলি, এবং বহিরাগত সত্ত্বা যা এটি ইন্টারেক্ট করে) আছে তার সাথে সম্পর্কগুলি বর্ণনা করে। 

### System scope and responsibilities

সিস্টেমের সুযোগ এবং দায়িত্বগুলি তার লক্ষ্যগুলি পূরণ করার জন্য সিস্টেমটি কী করতে হবে তা সংজ্ঞায়িত করে। তাদের ওয়েবসাইটে মতে, এই লাইব্রেরির বিটকয়েন প্রোটোকলের সাথে কাজ করার জন্য তৈরি করা হয়েছে। সিস্টেমের সবচেয়ে গুরুত্বপূর্ণ দায়িত্ব হল:

1. একটি ওয়ালেট বজায় রাখা, Bitcoin কোর একটি স্থানীয় কপি প্রয়োজন ছাড়া লেনদেন প্রেরণ / গ্রহণ।
2. একটি লাইটওয়েট সরলীকৃত পেমেন্ট যাচাইকরণ মোড প্রদান।
3. এনক্রিপশন, ফি গণনা, প্লাগযোগ্য মুদ্রা নির্বাচন / মুদ্রা নিয়ন্ত্রণ, এক্সটেনশান সমর্থন এবং ইভেন্ট শ্রোতাদের সাথে একটি ওয়ালেট ক্লাস প্রদান করে যা আপনাকে আপনার ভারসাম্য পরিবর্তনের সাথে আপ টু ডেট থাকতে দেয়।
4. উভয় async এবং থ্রেড-প্রতি-সংযোগ প্রদান।
5. একটি সাধারণ GUI wallet অ্যাপ্লিকেশন যা আপনি নিজের অ্যাপ্লিকেশনের জন্য ভিত্তি হিসাবে ব্যবহার করতে পারেন।
6. অ্যাপ্লিকেশন বাস্তবায়ন যা বিটকয়েনের বৈশিষ্ট্যগুলি ব্যবহার করে।

### External entities and interfaces

As described in the book [[7]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references), external entities are systems/people/organizations that interact with bitcoinj in some way. There are many external entities surrounding the bitcoinj’s environment. In this section, they can be found on Figure 3 and the most important ones are described.

![ContextView](ContextView.png)
*Figure 3: External Entities and Interfaces Diagram*

### Development

- Programming Language:
  
  Bitcoinj has been developed using **Java**. Indeed, Java is a well-known language, so everybody can contribute easily if wanted.

- Developed with and License required: 

  Since core developers use Java, they don’t recommend any Java Development Tool: any of them will do, as long as it supports Java 6 and Java 8. This way, each contributors can use the software they want. For instance, the main Java IDE are **Eclipse** and **IntelliJ** which are free and powerful tools. However, the core developers use **Maven 3+** which is a project management tool provided by Apache. Thus, you have to have an **Apache Licence** [[10]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references). Otherwise, users of bitcoinj can use **Gradle** if they prefer this tool.

- Implemented with and language which can be used:
  
  Considering bitcoinj is a library, it is used to create applications. To realize them, application developers have to implement the library in their own source code. Hopefully for application developers, bitcoinj is supported by a lot of softwares which can use Java to another programming language. 
   
   For example, 
  - **Jython**: From Java to Python.
  - **JRuby**: From Java to Ruby.
  
   are recommended by core developers.
   
   Afterwards, application developers can use a lot of different programming languages to develop their own application and use at the same time bitcoinj library. They can include **Java, Python, Ruby, C, C++, C#, .NET, JavaScript and Lisp** [[13]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references). 

- Library test:

  Core developers of bitcoinj recommend **BitCoin Core 0.9**. This tool enables contributors to test their code on an application which is already linked to the blockchain and uses the Bitcoin network [[14]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references).

- Hardware communication:

  Serialization and hardware communications have to be done to allow communication between several softwares, and exchange information on a network [[11]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references). In this way, bitcoinj uses **Google Protocol Buffer** [[10]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references), which is a tool developed by Google. In the case of bitcoinj, it is used for the Wallet class, micropayment transaction by setting bits format [[12]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references).

- Supported by:

  As long as you can develop your own application or contribute to bitcoinj library (in Java). You can use any Operating System like **Windows, MAC OS or Linux**.
  
### Feedback and developers

- Version Control and tracker issue:

  On each modification, versions control or issues tracking are done on **GitHub** platform between contributors and core developers. This tool allows contributors to help the core development team without destroying all their efforts. Today there are 84 contributors, more than 2900 commits and 187 issues listed on bitcoinj’s github.
  
  - Developers: 
  
  Developers can be separated in two branches. First of all, there is the team of **core developers : 1.  Mike Hearn 2. Andreas Schildbach**. Next, there is the **community** which can contribute to the project by different ways. In any case, to contribute to the project, core developers have to accept the contributor pull-requests (cf. [Stackholders analysis](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#stakeholders-analysis))
  
- Communication:

  To communicate with the bitcoinj community (Users and contributors), core developers have developed an **IRC Channel** and a **Google+** account where they communicate information on new release. People can also use the **mailing list** for asking questions, and the **Issues DB** for searching and reporting problems. 

### Users

- Users:

  Concerning Users, there are mainly **developers of Bitcoin application**. Indeed, bitcoinj is a library which aims helping in the creation of applications which would support Bitcoin digital wallets. (cf. [Stackholders analysis](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#stakeholders-analysis))

- Used by:

  Bitcoinj’s website referred a mainly users. This is **BitCoin Wallet**, an android application to manage your virtual wallet. this application have reached 16 000 download only on GooglePlay store.

## Development view

### Module organization

In this section, the module organization of bitcoinj is described.  As it has been mentioned before, bitcoinj is a library which has been implemented using Java. While developing the bitcoinj API, the developers have been focusing on the SPV (Simplified Payment Verification) smartphone wallet, as they defined it as their priority. That is the reason why the features of the API concern mainly the wallet. The information that is present in the table below (cf. Table 3) has been extracted from the Javadoc (cf. source [[15]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references)) and reformulated. For more details, refer to the Javadoc.

Modules for bitcoinj library are actually java packages.

*Table 3: Module description*

| Package name                 | Description                                                | Dependencies               |
| ---------------------------- |:-----------------------------------------------------------|:---------------------------|
| core                         |This package contains almost all that is needed for basic tasks for Bitcoin. It contains classes needed for network messages, such as the Block and Transaction classes, but also the PeerGroup class used for peer connectivity and more for block chain management. | core.listeners, crypto, net, net.discovery, script, store, utils, wallet |
| core.listeners               |This package is a sub-package of the core package. It contains all the listeners required by the core packages. | core, wallet |
| crypto | This package contains classes which implement the cryptographic part of the library. | core, wallet |
| jni | "jni" stands for Java Native Interface. This package contains classes enabling events to be relayed to native C++ objects. | core, core.listeners, protocols.channels, script, wallet, wallet.listeners |
| kits | This package contains the WalletAppKit class, which can be used to set up a new app requiring an SPV (Simplified Payment Verification) wallet. | core, core.listeners, net.discovery, store, wallet |
| net | This package contains classes which can handle low level network management. | core |
| net.discovery | This package contains classes that are used to discover peers in the P2P (peer-to-peer) network. | core |
| params | This package contains classes which have information about the network parameters of the different Bitcoin networks. | core, store, utils |
| protocols | This package contains two packages: channels and payments. | None |
| protocols.channels | This package contains classes which implement the micropayment channels. Tiny payments can be made rapidly using micropayment channels, if a channel has been set up. | core, crypto, script, wallet |
| protocols.payments | This package contains classes which implement a protocol used for wrapping Bitcoin transactions. The protocol sends to the receiver transactions the sender made, with metadata. | core, crypto, uri, wallet |
| script | This package contains classes which can work and execute Bitcoin script programs. | core, crypto |
| signers | This package contains a class which can calculate signatures over transactions. | core, crypto, script, wallet |
| store | Blockchain data which are downloaded from remote peers are kept in the block stores. | core |
| uri | This package contains a class which can parse and handle bitcoin. | core |
| utils | This package contains utility classes which are useful when it comes to money: monetary amounts, exchange rates, loading saved block files and more. | core, store |
| wallet | This package contains classes supporting the Wallet class. Different features are available for the Wallet, but it mainly can find and save transactions relevant to a set of keys or scripts. The Wallet class also knows how to calculate balances and spend money. | core, core.listeners, crypto, script, signers, utils, wallet.listeners |
| wallet.listeners | This package is a sub-package of the wallet package. It contains all the listeners required by the wallet package. | wallet |

#### Module dependencies

Refering to the “Context.md” file, in the “designdocs” folder of the bitcoinj github repository,
it is explained that the developers “have ended up with an often confusing mishmash of duplicate settings and odd dependencies between objects” (see below).

> However unlike many APIs, we have never had a more general notion of context and as the library has grown we have ended up with an often confusing mishmash of duplicate settings and odd dependencies between objects. For example several parts of the library want to throw away data once a transaction is confirmed enough that we don't expect it to ever be re-orgd out of the chain, but there's no agreement on how deep that should be. The Wallet stores files, as does the block store, as does Orchid (Tor support), but each component must be told where to put this data individually. The problem gets worse on Android, where there are no JAR files and data must be shipped as external files. On this platform components that want to load data files must be configured with a path to their files individually and there's no central list of what components need this. [[16]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references)

As it is shown on the figure 4, the bitcoinj library does not have a structure defined concerning the module dependencies. Indeed, there are a lot of dependencies and interdependencies existing between the modules, which makes difficult to establish a structure.

![module_dependencies](ModuleDependencies.png)

*Figure 4: Module dependencies in bitcoinj library*

Consequently, this library does not have a delimited architecture, since no layer can be properly defined.

However, we can identify some main modules, such as the core module and the wallet modules.Indeed, all the modules depend on the core module, which contains some important classes which can achieve the basic Bitcoin tasks. For example, it contains the Transaction and the Block classes.Also, a majority of modules depends on the wallet module, which was the priority for the developers. Thus, these modules can be considered as the core modules of the bitcoinj library, even though there is no structure which can be noticed.

### Codeline organization

In this section, we will describe how the source code of bitcoinj is stored in a directory structure and how it is built and tested regularly. The codeline organization is important in an open source system, since it makes easier to everyone to use, understand and test it. A well-defined codeline organization has the potential of greatly simplifying the development process.

An overview of the directories of the bitcoinj is shown in the figure 5 and a description following the diagram.

![Directories of bitcoinj repository](Codeline_Organization.jpeg)

*Figure 5: Overview of directories in bitcoinj repository*

*Table 4: Directory description*

| Directory name               | Description                                                | 
| ---------------------------- |:-----------------------------------------------------------|
| core                         |This directory contains almost all that is needed for basic tasks for Bitcoin. It includes all the modules described in the previous section such as classes needed for network messages, but also the PeerGroup class used for peer connectivity and more for block chain management. | 
| designdocs                   | This directory contains documentation for API explanations of bitcoinj and development guides.|
| examples                     | This directory contains modules written in Java, Javascript and Python (Jython). As it could be observed by the name, in this directory, users can find examples of how to use bitcoinj with the mentioned programming languages. By understanding these files, the user can then easily build its own application.|
| tools                        |This directory contains additional tools that are useful for development, like build functionality, automated testing libraries, and also documentation about the usage of it.|
| wallettemplate               |This directory contains classes supporting the Wallet class. Different features are available for the Wallet. It includes also two other directories, controls and utils which implement tasks like: validating the bitcoin address and other GUI features. |


### Source management
	 	
The bitcoinj repository is located on GitHub. When users want to contribute, it is recommended to open an issue for the proposed changes before starting development. The user forks the repository and makes their changes in a separate branch. When they have completed their work, they can request the code to be merged into the main repository by issuing a pull request which is reviewed then by the developers.


### Standardization of design

As most of open source systems, bitcoinj is developed by a team, and everyone can contribute to the github repository.  That is why the standardization of design is very important: it ensures the ease of the maintainability, the reliability and the technical cohesion of the system. That helps to minimize the technical debt, therefore to decrease the development time of new features and to speed up on fixing bugs.
Bitcoinj’s standardization design is basically based on the BIPs (Bitcoin Improvement Proposals).
As it is said in the bitcoinj standard support, “The BIPs are the communities” way of standardising new extensions and protocols that build on top of Bitcoin”. They can also be just ways of communicating new ideas. There are three types of BIPs [[18]](https://en.bitcoin.it/wiki/Bitcoin_Improvement_Proposals):
- Standards Track BIPs for changes to the network protocol, the validation or not of transactions, or anything related to interoperability.
- Informational BIPs for design issues or general guidelines.
- Process BIPs which describe or propose a change in process.
 As a library, bitcoinj provides API’s that we can use to implement most of these standards more easily.
Here are the supported BIPs [[19]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references):

| BIP number        | Name                | Relevant API           |
| ---------------------------- |:---------------------------|:---------------------|
| 11                   | m-of-n multisig transactions | ScriptBuilder |
| 14                | Protocol version and user agent | PeerGroup.setUserAgent |
| 16                | Pay to script hash (P2SH) | Address |
| 21                | Bitcoin URI scheme | BitcoinURI |
| 31                | Ping/pong messages | Peer.ping() |
| 32                | HD wallets | DeterministicKeyChain) |
| 35                | mempool message | used automatically |
| 37                | Bloom filtering | PeerFilterProvider (used automatically) |
| 39                | Mnemonic codes for representing private keys | MnemonicCode |
| 70,72             | Payment protocol | PaymentSession |
| 38                | Encrypted private key serialization | BIP38PrivateKey |
                                                


### Standardization of testing

Standardization of testing is always a good practice and it helps to make the testing processes faster. Bitcoinj uses different test modules for testing to ensure the quality and security. In this section are discussed the test modules. [[20]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references)

- The testNet:

  Testnet is a network for testing project and it gives access for testing the experimental features. In bitcoinj, it’s very useful to test the project by the application developers and testers through testnet because this network use coins that has no value unlike real bitcoins. To be able to test the app using testnet by representing the object as **TestNetParams.get()**. The wallet-tool app   accepts a flag  **--net=TEST**.
  
 - Regression test mode:

   There is an another mode of testing in bitcoinj which is regtest. We need network params, **RegTestParams.get()** to run regtest mode and it will run locally. Wallet-tool can also use this mode by   **--net=REGTEST--peers=localhost**.
  
 - Unit tests:

   Unit testing is very important in any projects. There is a TestUtils class in bitcoinj which provides various test cases and run to manufacture fake transactions. Travi-CI is a hosted continuous service used to build and test projects which are hosted by GitHub [[21]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references). Mainly, it runs tests every time anyone commits in GitHub and we can see from the project structure of bitcoinj that it includes a file  called **.travis.yml** which automatically build and run test cases to test the application.
  
## Analysis of a Quality Attribute: Usability

The usability of a system is very important, and the developers should focus on that all along the implementation because there is no sense to create something which will not be used in the future. To be used, a system has to be user-friendly: people are reluctant when it comes to use something which is not intuitive. It means that what is created must have be easy to use and learn. Besides, a system is good if the user learns fast how to use it efficiently, if the system minimizes the impact of errors or displays the relevant ones. Basically, it should give satisfaction to the user as well as increasing confidence. Considering bitcoinj has been built to work with the Bitcoin protocol, it is very important that the user has confidence in it because money will be managed at some point.

### BitcoinJ a user-friendly library

First of all, bitcoinj can be considered as user-friendly. Indeed, developers have included a complete tutorial to install and set up bitcoinj library, and to start developping your own Bitcoin wallet application. 
In this tutorial, they explain how to obtain the recent source code and the basic objects used by bitcoinj. 

![Initial_Setup](Initial_Setup.png)

*Figure 6: Setup Architecture for bitcoinj*

A built-in logging and assertions are present on bitcoinj, hence, users just have to be preoccupied by the logging system they want to use. By default, developers recommend to use the simple logger with the most of standard errors possibilities.

Getting the source code of bitcoinj, users have to use Maven or Gradle as a build system. From Git, they have to drag the code from the source repository to Maven. It is the recommended and safest way to get it. To make sure to have the latest version of bitcoinj’s code, users can use Maven or Gradle guide and use run commands.

At this point, users can use the library bitcoinj and **basic structures** of it.

![Basic_structure](Basic_structure.png)

*Figure 7: Interconnection of instances*

Hopefully for users, bitcoinj’s developer have implemented basic objects to use their library. It exists seven of them:

- **NetworkParameters**. This object allow users to select the network they want (production or test).

- The network connections is managed by **PeerGroup** instance.

- **Wallet**. Instance to store your public and private keys (ECKeys) and other data.

- The management of shared, global data structure is linked to **BlockChain** object. Without this object, Bitcoin couldn’t work.

- **BlockStore** instance. To keep in memory the block chain data structure 

- Wallet events are received on **WalletEventListener** implementations.

All these instances have to be interconnected. If they are not, data could not go from one instance to the other. Indeed, each object need each other to proceed correctly.

To avoid these interconnection problems, developers of bitcoinj have added a feature to do it automatically. This is the **WalletAppKit** object. However, they suggest to do it manually if you want to create the application which fits the most with your needs. As a Usable project, developers have detailed all instructions to do it on this web page: [[22]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references)

After having set up correctly the library, the users can start to work on it. Thankfully for users, developers have include a lot of tutorials and a well detailed Java Documentation (cf. source [[15]](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#references) and [Module organization](https://github.com/it-teaching-abo-akademi/sa-2017-software_architecture_group-2-1/blob/master/BitcoinJ.md#module-organization)) to avoid errors and development mistakes when they use their library. At the same time, users can watch Youtube Tutorials to realize simple or complex features for their own wallet. For example, they can follow this video to [Build a simple GUI wallet](https://www.youtube.com/watch?v=9AK11JsZWVo).

### Usability as a way of bug tracking, improvement and assistance

BitcoinJ is a library and does not provide any report issues or users assistance in its own body. However, core developers of bitcoinj have set up with help of **Google Mailing List** and **GitHub** a system of issues reporting, users assistance and bitcoinj improvements. 

![BugTrackingAndImprovement](Issue_and_improv.png)

*Figure 8: bitcoinJ bugtracking, improvement and users assistance*

If users want to report a bug or an issue, they can post their report on the following [Issues DataBase](https://github.com/bitcoinj/bitcoinj/issues). 

Furthermore, users can add different tags according to the subject and the criticality of their issue(s) and/or bug(s). 

On the other hand, users can add a request to a [Google mailing list](https://groups.google.com/forum/#!forum/bitcoinj)  if they have any hesitation on the bitcoinJ utilization or if they have ideas to improve the library.
At this moment, the mailing list reference more than 2000 subjects. Having the efficient way to help or improve the library, authors of subjects can have a response from core developers and/or members of bitcoinj community.

### ক্ষুদ্রতম ত্রুটি

এছাড়াও, এটি অনেক বার আগে উল্লেখ করা হয়েছে, বিটকয়েন একটি লাইব্রেরি: এটি সফ্টওয়্যার উন্নয়নশীল ব্যবহৃত সম্পদ একটি সংগ্রহ, এর অর্থ এটা কোন গ্রাফিক ইউজার ইন্টারফেস নেই। ফলস্বরূপ, এই লাইব্রেরিটির ব্যবহারযোগ্যতা কিছু ভিজ্যুয়াল ডিজাইনের উল্লেখ করে অনুমান করা যায় না, যেহেতু কোনওটি নেই।
যাইহোক, আমরা উত্থাপন করা যেতে পারে যে ব্যতিক্রম পড়ুন। জাভাতে বাস্তবায়িত হলে, এটি জাভাতে একটি অ্যাপ্লিকেশন এবং সেইসঙ্গে যে কোন JVM সামঞ্জস্যপূর্ণ ভাষা তৈরির সময় ব্যবহার করা যেতে পারে। লাইব্রেরির সাহায্যে প্রোগ্রামটি চালানোর সময় সিস্টেম ত্রুটিগুলি কনসোলটিতে প্রদর্শন করা হয়।

### Learnability

লাইব্রেরি আরও শেখার জন্য, উদাহরণগুলি জাভা, জাভাস্ক্রিপ্ট বা পাইথনের সাথে বিটকুইজ ব্যবহার করে ব্যাখ্যা করা হয়। এই উদাহরণগুলি ফোল্ডারে পাওয়া যাবে যার পাথ “bitcoinj/examples/src/main/”। তাদের সব সম্পূর্ণরূপে মন্তব্য করা হয় যাতে ব্যবহারকারী সহজেই বুঝতে পারেন কিভাবে এটি কাজ করে এবং কিভাবে এগিয়ে যেতে হয় যখন এটি নিজস্ব অ্যাপ্লিকেশন তৈরি করতে আসে।


## উপসংহার

এই ডকুমেন্টেশনটিতে আমরা বেশীরভাগ স্থাপত্যের মতামত ও দৃষ্টিকোণতে বিটকুইজকে সংক্ষিপ্ত করে তুলেছি, পাঠককে বুঝতে সক্ষম হতে, সিস্টেমের একটি বিস্তৃত ধারণা পেতে এবং প্রকল্পে অবদান রাখতে সহায়তা করে। এই সিস্টেমের বিশ্লেষণের সময় এটি লক্ষ্য করা গেছে যে বিটকয়েনের একটি খুব জটিল স্থাপত্য রয়েছে।

প্রথম বিভাগে, লাইব্রেরি চালু করার পরে, আমরা এই সিস্টেমের মধ্যে উপস্থিত বিভিন্ন অংশীদারদের চিহ্নিত করেছি। বিটকিন্গের স্টেকহোল্ডারদের একটি সমৃদ্ধ পরিবেশ রয়েছে যা লাইব্রেরিতে ব্যবহার এবং / অথবা অবদান রাখে। আমরা সর্বাপেক্ষা গুরুত্বপূর্ণ ব্যক্তিদের নিয়ে কথা বললাম এবং তাদের চারটি বিভাগে বিভক্ত করে দেখিয়েছি যে তাদের প্রকল্পে কম / উচ্চ সুদের / ক্ষমতা থাকলে।

বিটকয়েনের বিভিন্ন স্থাপত্য বিশ্লেষণের ফলে আমরা এমন একটি প্রকল্প সম্পর্কে পরিচিত হতে পেরেছি, যা অনেকের কাছে বেশ পরিচিত। প্রেক্ষাপটে দর্শনের বর্ণনাটি আমাদেরকে বিটকুইজটি তৈরি, বাস্তবায়িত, পরীক্ষিত, ব্যবহার করা, সমন্বিত এবং অন্যান্য গুরুত্বপূর্ণ বৈশিষ্ট্যগুলির মাধ্যমে সনাক্ত করা যায়।

বিকাশের দৃষ্টিভঙ্গি সম্পর্কে কথা বলার, বিটকয়েনের উন্নয়নের নীতিমালাগুলি দেওয়া হয়েছে। আমরা Github সংগ্রহস্থল পাওয়া প্রতিটি প্যাকেজ এবং মডিউল বিশদ বিবরণ এবং ব্যাখ্যা। উন্নয়ন দেখুন কিছু পরীক্ষার এবং নকশা মান চিহ্নিত।
 
সহজলভ্যতা এবং সহজলভ্য একসাথে এই লাইব্রেরিটি খুব আকর্ষণীয় করে তোলে। আমরা বিটকয়েন একটি ভাল মানের বৈশিষ্ট্য হিসাবে ব্যবহারযোগ্যতা চয়ন কেন যে

বিটকয়েনের সামগ্রিক বিশ্লেষণটি দেখায় যে এই ধরনের প্রকল্পগুলি প্রকৃতপক্ষে ওপেন-সোর্স পরিবেশ থেকে উপকার লাভ করে। কিন্তু অন্যদিকে, আমরা বুঝতে পেরেছি যে প্রোগ্রামাররা খুব জটিল এবং স্পষ্টভাবে নির্ধারিত স্থাপত্যের সাথে শেষ হয়নি। একটি সুনির্দিষ্ট সংজ্ঞায়িত স্থাপত্য না থাকার ফলে ভবিষ্যতের অংশীদারদের জন্য জিনিসগুলি আরও কঠিন হয়ে ওঠে, কারন এটি বাস্তবায়ন কীভাবে বোঝে তা আরো সময় ব্যয় করতে হবে। যদিও আমরা একটি আর্কিটেকচার এক্সট্রাক্ট করতে সক্ষম ছিলাম না, তবে এখানে কোনও বিষয় নেই, এটি আমাদের জন্য একটি ভাল অভিজ্ঞতা ছিল, তাই আমরা কিছু সফটওয়্যার ডেভেলপ করার সময় কী কী এড়ানোর কথা জানি

## তথ্যসূত্র
[1] Blockchain France. (2017). Qu’est-ce que la blockchain ?. [online] Available at: https://blockchainfrance.net/decouvrir-la-blockchain/c-est-quoi-la-blockchain/ [Accessed 18 Sep. 2017].

[2] CoinDesk. (2017). CoinDesk - Guides. [online] Available at: https://www.coindesk.com/information [Accessed 18 Sep. 2017].

[3] How Bitcoin Works in 5 Minutes (Technical). (13 Apr. 2014). [video] Available at: https://www.youtube.com/watch?v=l9jOJk30eQs [Accessed 18 Sep. 2017].

[4] Bitcoin - Heu?reka #13. (25 Apr. 2016) [video] Available at: https://www.youtube.com/watch?v=h4XZpkrpIbs [Accessed 18 Sep. 2017]

[5] Le Bitcoin et la Blockchain (avec Heu?Reka) — Science étonnante #31. (24 Jun. 2016). [video] Available at: https://www.youtube.com/watch?v=du34gPopY5Y [Accessed 18 Sep. 2017].

[6] MASSE, A. and REJANI, Z. (2015). Argent et Société. [online] Argent et Société. Available at: https://argentetsociete.wordpress.com/ [Accessed 18 Sep. 2017].

[7] Nick Rozanski and Eoin Woods. Software Systems Architecture: Working with Stakeholders using Viewpoints and Perspectives. Addison-Wesley, 2012.

[8] bitcoin wiki. (2016). bitcoinj. [online] Available at: https://en.bitcoin.it/wiki/Bitcoinj [Accessed 26 Sep. 2017].

[9] GitHub. (2017). bitcoinj. [online] Available at: https://github.com/orgs/bitcoinj/people [Accessed 26 Sep. 2017].

[10] GitHub. (2017). bitcoinj/bitcoinj. [online] Available at: https://github.com/bitcoinj/bitcoinj/blob/master/README.md [Accessed 28 Sep. 2017].

[11] Google Protocol Buffers Documentation. (2017). Google Developers. [online] Available at : https://developers.google.com/protocol-buffers/docs/overview [Accessed 28 Sep. 2017]

[12] Bitcoinj.github.io. (2017). Working with bitcoinj. [online] Available at: https://bitcoinj.github.io/working-with-bitcoinj [Accessed 28 Sep. 2017].

[13] Bitcoinj.github.io. (2017). How to access bitcoinj from other languages. [online] Available at: https://bitcoinj.github.io/using-from-other-languages [Accessed 28 Sep. 2017].

[14] Bitcoinj.github.io. (2017). How to test applications. [online] Available at: https://bitcoinj.github.io/testing [Accessed 28 Sep. 2017].

[15] Javadoc bitcoinj 0.14 API. (2017) bitcoinj. [online] Available at: https://bitcoinj.github.io/javadoc/0.14/ [Accessed 30 Sep. 2017]

[16] Context. (21 Mar. 2015). bitcoinj/bitcoinj/blob/master/designdocs. [online] Available at: https://github.com/bitcoinj/bitcoinj/blob/master/designdocs/Contexts.md [Accessed 02 Oct. 2017]

[18] https://en.bitcoin.it/wiki/Bitcoin_Improvement_Proposals

[19] https://bitcoinj.github.io/bitcoin-standards

[20] Bitcoinj.github.io. (2017). How to test applications . [online] Available at: https://bitcoinj.github.io/testing [Accessed 08 Oct. 
17].

[21] En.wikipedia.org. (2017). Travis CI . [online] Available at: https://en.wikipedia.org/wiki/Travis_CI [Accessed 08 Oct. 2017].

[22] Bitcoinj.github.io. (2017). Getting started in Java. [online] Available at: https://bitcoinj.github.io/getting-started-java [Accessed 8 Oct. 2017].

[23] GitHub. (2017). bitcoinj/bitcoinj. [online] Available at: https://github.com/bitcoinj/bitcoinj/issues [Accessed 8 Oct. 2017].
