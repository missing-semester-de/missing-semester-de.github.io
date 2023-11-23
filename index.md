---
layout: page
title: Das fehlender Semester deines Informatikstudiums 
nositetitle: true
---
Kurse und Vorlesungen lehren über anspruchsvolle Themen in der Informatik: von Betriebssystemen
bis maschinelles Lernen, aber es gibt ein fundamentales Thema das selten abgedeckt wird und 
stattdessen den Studenten in Eigenarbeit überlassen wird:
Der Umgang mit Konsolen & Werkzeugen. Wir zeigen dir, wie du mit der Kommandozeile umgehst und 
im handumdrehen ein leistungsstarkes Textbearbeitungsprogramm, Versionskontrollsysteme und vieles mehr lernst!


Studierende verbringen im Laufe ihres Studiums viele Stunden, um mit diesen fundamentalen Tools umzugehen, 
daher ist es sinnvoll den Umgang mit diesen Werkzeugen zu erlernen, um den Umgang mit diesen zu verbessern.
Wir helfen dir dabei durch den Dschungel der Tools durchzusteigen und deine Arbeit mit diesen effizenter zu
gestalten.

Erfahre mehr über die [Motivation dieses Kurses](/about/).

{% comment %}
# Registrierung

Melden Sie sich für den Kurs IAP 2020 an, [indem Sie dieses Formular ausfüllen](https://forms.gle/TD1KnwCSV52qexVt9).
{% endcomment %}

# Termine

{% comment %}
**Lecture**: 35-225, 2pm--3pm<br>
**Office hours**: 32-G9 lounge, 3pm--4pm (every day, right after lecture)
{% endcomment %}

<ul>
{% assign lectures = site['2020'] | sort: 'date' %}
{% for lecture in lectures %}
    {% if lecture.phony != true %}
        <li>
        <strong>{{ lecture.date | date: '%-m/%d/%y' }}</strong>:
        {% if lecture.ready %}
            <a href="{{ lecture.url }}">{{ lecture.title }}</a>
        {% else %}
            {{ lecture.title }} {% if lecture.noclass %}[no class]{% endif %}
        {% endif %}
        </li>
    {% endif %}
{% endfor %}
</ul>

Alle Vorlesungen sind verfügbar [auf
YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J).

# Über diesen Kurs

**Dozierende**: Die Dozenten dieses Kurses sind [Anish](https://www.anishathalye.com/), [Jon](https://thesquareplanet.com/), und [Jose](http://josejg.com/).<br>
**Fragen**: Schreib uns eine Mail an: [missing-semester@mit.edu](mailto:missing-semester@mit.edu).

# Über das MIT hinaus

Wir haben diesen Kurs auch über das MIT hinaus veröffentlicht, in der Hoffnung das andere von diesen profitieren können.
Beiträge und Disskusionen darüber können sie auf folgenden Webseiten finden:

 - [Hacker News](https://news.ycombinator.com/item?id=22226380)
 - [Lobsters](https://lobste.rs/s/ti1k98/missing_semester_your_cs_education_mit)
 - [/r/learnprogramming](https://www.reddit.com/r/learnprogramming/comments/eyagda/the_missing_semester_of_your_cs_education_mit/)
 - [/r/programming](https://www.reddit.com/r/programming/comments/eyagcd/the_missing_semester_of_your_cs_education_mit/)
 - [Twitter](https://twitter.com/jonhoo/status/1224383452591509507)
 - [YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J)

{% comment %}
Some more URLs:

- https://news.ycombinator.com/item?id=27154577
- https://news.ycombinator.com/item?id=34934216
- https://www.reddit.com/r/learnprogramming/comments/nca1v3/mit_the_missing_semester_of_your_cs_education/
- https://www.reddit.com/r/compsci/comments/eyywv8/the_missing_semester_of_your_cs_education_from_mit/
- https://www.reddit.com/r/programming/comments/io7nq3/the_missing_semester_of_your_cs_education_mit/
- https://twitter.com/MIT_CSAIL/status/1349766980413263873
- https://twitter.com/MIT_CSAIL/status/1481676163491659780
- https://twitter.com/MIT_CSAIL/status/1581313961093484545
{% endcomment %}

# Übersetzungen

- [Chinesisch (vereinfacht)](https://missing-semester-cn.github.io/)
- [Chinesisch (traditionell)](https://missing-semester-zh-hant.github.io/)
- [Japanisch](https://missing-semester-jp.github.io/)
- [Koreanisch](https://missing-semester-kr.github.io/)
- [Portugisisch](https://missing-semester-pt.github.io/)
- [Russisch](https://missing-semester-rus.github.io/)
- [Serbisch](https://netboxify.com/missing-semester/)
- [Spanisch](https://missing-semester-esp.github.io/)
- [Türkisch](https://missing-semester-tr.github.io/)
- [Vietnamesisch](https://missing-semester-vn.github.io/)
- [Arabisch](https://missing-semester-ar.github.io/)
- [Italienisch](https://missing-semester-it.github.io/)
- [Persisch](https://missing-semester-fa.github.io/)
- [Deutsch](link-missing!)

Hinweis: Es handelt sich um externe Links zu Übersetzungen, die von der Community erstellt wurden.
Wir haben diese nicht verifiziert.

Hast du eine Übersetzung der Notizen für diese Klasse? Erstelle einen 
[Pull Request](https://github.com/missing-semester/missing-semester/pulls) damit
wir diese der Liste anfügen können!

## Danksagungen

Wir Danken Elaine Mello, Jim Cain, und [MIT Open
Learning](https://openlearning.mit.edu/) es uns zu ermöglichen die Vorlesungen aufzunehmen;
Anthony Zolnik und [MIT
AeroAstro](https://aeroastro.mit.edu/) für Audio und Videoequipment; und Brandi Adams sowie
[MIT EECS](https://www.eecs.mit.edu/) für die Unterstüzung dieses Kurses.

---

<div class="small center">
<p><a href="https://github.com/missing-semester/missing-semester">Quelltext</a>.</p>
<p>Lizensiert unter CC BY-NC-SA.</p>
<p>Schaue <a href="/license/">hier</a> um selber beizutragen &amp; für die Übersetzungsrichtlinien.</p>
</div>
