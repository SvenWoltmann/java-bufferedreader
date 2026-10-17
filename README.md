# Java BufferedReader

[![Build](https://github.com/SvenWoltmann/java-bufferedreader/actions/workflows/build.yml/badge.svg)](https://github.com/SvenWoltmann/java-bufferedreader/actions/workflows/build.yml)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=SvenWoltmann_java-bufferedreader&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=SvenWoltmann_java-bufferedreader)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=SvenWoltmann_java-bufferedreader&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=SvenWoltmann_java-bufferedreader)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=SvenWoltmann_java-bufferedreader&metric=security_rating)](https://sonarcloud.io/dashboard?id=SvenWoltmann_java-bufferedreader)

## Article

The code refers to the following articles (not yet published):
* English: [Java BufferedReader](https://www.happycoders.eu/java/java-bufferedreader/)
* German: [Java BufferedReader](https://www.happycoders.eu/de/java/java-bufferedreader/)

## Contents

Most examples read the small log file `files/server.log`. Every class with a `main()` method in `eu.happycoders.bufferedreader` is one chapter of the article and prints the outputs shown there. Run one from the repository root with `java -cp target/classes eu.happycoders.bufferedreader.<ClassName>` after `mvn compile`. Files the examples create go into `target/`.

* `Intro` – reads the log file line by line
* `Ch1Creating` – `Files.newBufferedReader()`, `FileReader`, `InputStreamReader` around a `GZIPInputStream`, an own buffer size, and a Latin-1 file read as UTF-8
* `Ch2ReadLine` – line terminators, empty lines, and the end of the input
* `Ch3Lines` – `lines()` with `filter()` and `groupingBy()`, an `UncheckedIOException` while streaming, and `Files.lines()`
* `Ch4ReadAll` – `readAllLines()` and `readAllAsString()` (Java 25), also after a `readLine()`
* `Ch5Characters` – `read()` and `read(char[], int, int)`
* `Ch6MarkReset` – an optional header line with `mark()` and `reset()`, and `skip()`
* `Ch6Ready` – `ready()` returns `false`, yet the next `readLine()` returns a line
* `Ch7Console` – reading lines from `System.in` with the charset from `stdin.encoding` (Java 25)
* `Ch7Readln` – `IO.readln()` (Java 25)
* `Ch8Scanner` – tokens with `Scanner` and with `split()`, and how both classes report an `IOException`
* `Ch9Closing` – closing the `BufferedReader` closes the reader inside it
* `Ch10Mistakes` – calling `readLine()` twice per loop iteration

## Benchmarks

The package `eu.happycoders.bufferedreader.benchmark` contains the JMH benchmarks of the article's performance section:

* `ReadBenchmark` – reading a 100,000,000-byte UTF-8 text file with `InputStreamReader`, `FileReader`, and `BufferedReader` (`read()`, `read(char[])`, `readLine()`, `lines()`, `readAllLines()`), and with `Scanner.nextLine()`
* `BufferSizeBenchmark` – `readLine()` with buffer sizes from 256 to 1,048,576 characters

The first run creates the test file `target/benchmark-input.txt` from a fixed seed, so every machine reads the same file. Build and run:

```
mvn package
java -jar target/benchmarks.jar
```

The complete run takes about 15 minutes. Close other applications while it runs.


<!-- happycoders-resources:start -->
<!-- Generated from happycoders-website-astro/data/github-readme by scripts/content/sync-github-readmes.mjs. Edit there, not here. -->

## <br>Additional Resources

### <br>Java Versions PDF Cheat Sheet

**Stay up-to-date** with the latest Java features with this **free** [PDF Cheat Sheet](https://www.happycoders.eu/java-versions/)!

[<img src="/img/java-versions-cheat-sheet-mockup.png" alt="Java Versions PDF Cheat Sheet Mockup" width="468">](https://www.happycoders.eu/java-versions/)

* Avoid lengthy research with this **concise overview of all Java versions from Java 10 to Java 27**.
* **Discover the innovative features** of each new Java version, summarized on a single page.
* **Impress your team** with your up-to-date knowledge of the latest Java version.

👉 [Download the free Java Versions PDF](https://www.happycoders.eu/java-versions/)<br>

_(Hier geht's zur deutschen Version &rarr; [Java-Versionen PDF](https://www.happycoders.eu/de/java-versionen/))_


### <br>The Big O Cheat Sheet

With this **free** [1-page PDF cheat sheet](https://www.happycoders.eu/big-o-cheat-sheet/), you'll always have the **7 most important complexity classes** at a glance.

[<img src="/img/big-o-cheat-sheet-mockup.png" alt="Big O PDF Cheat Sheet Mockup" width="304">](https://www.happycoders.eu/big-o-cheat-sheet/)

* **Always choose the most efficient data structures** and thus increase the performance of your applications.
* **Be prepared for technical interviews** and confidently present your algorithm knowledge.
* **Become a sought-after problem solver** and be known for systematically tackling complex problems.

👉 [Download the free Big O Cheat Sheet](https://www.happycoders.eu/big-o-cheat-sheet/)<br>

_(Hier geht's zur deutschen Version &rarr; [O-Notation Cheat Sheet](https://www.happycoders.eu/de/o-notation-cheat-sheet/))_


### <br>HappyCoders Newsletter
👉 Want to stay on top of modern Java?
Sign up for the [HappyCoders newsletter](https://www.happycoders.eu/newsletter/) – Modern Java: new versions & features, performance, and JVM insights – once a month.

_(Hier geht's zur deutschen Version &rarr; [HappyCoders-Newsletter deutsch](https://www.happycoders.eu/de/newsletter/))_


### <br>🇩🇪 An alle Java-Entwickler:innen, die durch fundierte Kenntnisse über Datenstrukturen besseren Code schreiben wollen

Trage dich jetzt unverbindlich auf die [Warteliste](https://www.happycoders.eu/de/mastering-data-structures-warteliste/) von „Mastering Data Structures in Java“ ein, und erhalte das beste Angebot!

[<img src="/img/mastering-data-structures-product-mockup.png" alt="Mastering Data Structures Mockup" width="640">](https://www.happycoders.eu/de/mastering-data-structures-warteliste/)

👉 [Zur Warteliste](https://www.happycoders.eu/de/mastering-data-structures-warteliste/)
<!-- happycoders-resources:end -->
