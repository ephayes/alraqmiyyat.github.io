---
header:
  image: /images/covers/03883u.jpg
  caption: "**Photo credit**: Kairouan. Bird’s-eye view taken from top of the minaret of the Grand Mosque showing the mosque proper and the cloisters of the great courtyard. *Library of Congress*, [LC-DIG-ppmsca-03883](http://hdl.loc.gov/loc.pnp/ppmsca.03883)"
title:			"Creating Frequency-Based Readers for Classical Arabic"
author:		Maxim Romanov
layout:		single
categories:
  - NLP
  - Arabic
  - Teaching
tags:
  - Blogpost
---

Learning classical Arabic is a long process. Most of us took great pleasure in advanced reading classes with our professors, but, often struggling with an overwhelming volume of new vocabulary, we also—at least occasionally—had a feeling that a traditional method is not necessarily the most effective one. While advanced students usually overcome this difficulty by their sheer passion for the subject, the introduction of excessive vocabulary creates a serious obstacle to less advanced yet capable students.

![image-right](/images/fbr/reader_cover.png){: .align-right-border}

Pervasive availability of electronic texts and computational methods of text analysis allows us to rethink how we teach difficult languages. We can identify the most frequent features within a corpus and focus our attention on them. For example, the 100 most frequent lexical items constitute about 56% of the entire vocabulary of over 34,000 Prophetic sayings (<em>ḥadīṯ</em>) from the Six [Sunnī] Collections (<em>al-kutub al-sittaŧ</em>, approximately 2.8 million words). Relying on such data, one can generate a frequency-based reader that will introduce students to the shortest texts with the most frequent vocabulary and grammatical structures. With a paced increase in difficulty of texts and incremental expansion of vocabulary, students are capable of digesting much larger volumes of text both in class and at home, and such an extended exposure enables students to internalize the authentic language more efficiently. For example, in the course of one semester, we managed to cover about 400 <em>ḥadīṯ</em>s, while at the same time reviewing the grammar of classical Arabic and having regular discussions of thematic readings that helped students to understand the cultural importance of the Ḥadīṯ across almost 14 centuries of Islamic history.<a href="#fn1" class="footnoteRef" id="fnref1"><sup>1</sup></a>
<p>While developed primarily with classical Arabic in mind, the approach is actually universal and can be used for any language. It works best with serialized texts—that is a large corpus of relatively short text of the same type (in the case of Arabic that would be <em>ḥadīṯ</em> collections, chronicles, biographical collections, poetic anthologies, contemporary newspapers, etc.). Considering that in terms of vocabulary various forms and genres may differ from each other quite significantly (Figure <a href="#fig:3000">1</a> shows that such difference may go up to 80%!), this method can be used to introduce students to the language of particular genres in the most efficient manner. Courses based on such readers can be a valuable addition to any language program and will be particularly welcomed by graduate students who often face the need to develop their readings skills as quickly and efficiently as possible.</p>

<a name="fig:3000"></a>
<figure class="fit">
	<a href="../images/fbr/3000a.png">
		<img src="../images/fbr/3000a.png">
	</a>
<figcaption><b>Figure 1.</b> The matrix shows lexical overlap across the frequency lists (top 3,000 items) that represent large thematic specimens of Arabic language. The specimens are arranged chronologically, staring with the earliest (right-top corner, 9<sup>th</sup> century) to the latest (20<sup>th</sup> century). The most dramatic lexical difference is between <em>al-Kutub al-Sittaŧ</em>, the Six [Sunnī] Collections of <em>ḥadīṯ</em>s, and <em>al-Šarḳ al-awsaṭ</em>, the modern newspaper: the frequency lists of these two sources (again, top 3,000 items) share only 20% of word forms (tokens). Even among the “classical” works the lexical distance is quite significant, with the percentage of shared vocabulary fluctuating mainly between 38% and 58% (for the interquartile range).
<br><br>
<strong>Texts compared</strong>: <em>al-Kutub al-Sittaŧ</em> (2,8 mln. words), the 6 Sunnī collections of Ḥadīṯ (~9<sup>th</sup> century CE); <em>Tafsīr al-Ṭabarī</em> (or <em>Ǧāmiʿ al-bayān</em>, 3 mln. words), a commentary to the Qurʾān of al-Ṭabarī (d. 310/922 CE); <em>Kitāb al-Aġānī</em> (1,5 mln. words), a poetic anthology of Abūl-l-Faraǧ al-Iṣbahānī (d. 356/967 CE); <em>al-Futūḥāt al-Makkiyyaŧ</em> (1,7 mln. words), an extensive Ṣūfī text of Ibn al-ʿArabī (d. 638/1240 CE); <em>Fatāwá Ibn Taymiyyaŧ</em> (2,9 mln. words), a collection of legal decisions and epistles of Ibn Taymiyyaŧ (d. 728/1327 CE); <em>Taʾrīḫ al-Islām</em> (3,2 mln. words), a biographical collection and chronicle of al-Ḏahabī (d. 748/1347 CE); <em>Maǧallaŧ al-Risālaŧ</em> (16 mln. words), an early 20<sup>th</sup>-century Egyptian literary journal; <em>Tafsīr al-Mīzān</em> (2,3 mln. words), a modern Šīʿī commentary to the Qurʾān of al-Sayyid al-Ṭabāṭabāʾī (d. 1981 CE); and <em>al-Šarḳ al-Awsaṭ</em> (2,5 mln. words), a modern Arabic newspaper (collected by Tariq Yousef from <a href="http://aawsat.com/" class="uri">http://aawsat.com/</a>).
</figcaption>
</figure>

<h2 id="description-of-the-method">Description of the method</h2>
<p>The overall procedure is rather simple and runs as described below.</p>
<p><em>Step I</em>. Ḥadīṯ collections were downloaded from <a href="http://sunnah.com/" class="uri">http://sunnah.com/</a>. Then, initial texts were reformatted and normalized.<a href="#fn2" class="footnoteRef" id="fnref2"><sup>2</sup></a> (There are multiple way how specimens of other genres can be obtained and the processed for a similar reader).</p>
<p><em>Step II</em>. All vocabulary from the corpus was collected and converted into a frequency list. This list was then converted into a ranking list, where the most frequent item receives rank 1, the second—2, the third—3, and so on; items with the same frequency are assigned the same rank. It should be noted that vocabulary items have not been parsed with a morphological analyser, so different forms of the same word are treated separately (i.e., <em>ḳāla</em>, <em>ḳīla</em>, <em>ḳālat</em>, <em>fa-ḳāla</em>, etc. have their own frequencies and ranked separately). The main reason for not using the results of automatic morphological analysis is largely technical, since existing morphological analyzers are meant to work with modern standard Arabic and do not perform well on classical Arabic.<a href="#fn3" class="footnoteRef" id="fnref3"><sup>3</sup></a> At the same time, using frequencies of word forms (tokens) rather than dictionary forms (lexemes) has its advantages, since more frequent forms will be given more frequently in the reading materials (such as, for example, very frequent <em>ḳāla</em> [sing. masc.] vs. rather rare <em>ḳālā</em> [dual masc.]).<a href="#fn4" class="footnoteRef" id="fnref4"><sup>4</sup></a></p>
<p><em>Step III</em>. The average mean of ranking values was calculated for each <em>ḥadīṯ</em>. The resultant values then served as difficulty indices, where texts with the most frequent vocabulary would have the lowest average means, and vice versa. These indices were then used as sorting values that allowed rearranging all 34,000 <em>ḥadīṯ</em>s by the difficulty of their vocabulary. The advantage of the average mean here is that even a single low frequency lexical item increases the difficulty index of a text, which is pushed down the list. This approach turned up a couple of unforeseen positive effects. First, as the length of a text increases so does the probability of more rare lexical items—as a result, the “easiest” texts are also the shortest ones. This convenient outcome allows students to begin with the shortest texts and move gradually to the longer ones. The second effect is that the most frequent vocabulary also tend to appear in the most frequent grammatical and syntactic structures.</p>
<p><em>Step IV</em>. The rearranged collections of ranked <em>ḥadīṯ</em>s was not quite useable, since this method also groups together items that are almost the same. Here manual input was required to exclude <em>ḥadīṯ</em>s that are too similar.</p>
<p><em>Step V</em>. At last, the selection of <em>ḥadīṯ</em>s was converted into format and typeset into the reader in front of you. As you will see, quite a few <em>ḥadīṯ</em>s in the beginning of the reader feature only <em>isnād</em>s, “the chains of transmitters”, and do not have <em>matn</em>s, the actual texts of <em>ḥadīṯ</em>s. I used these <em>matn</em>-less <em>ḥadīṯ</em>s to introduce students to the concept of transmission of knowledge in Islamic culture, which most were not familiar with; next time around I will modify the reader to avoid having very similar texts next to each other, which can be done by the retagging of the selection of <em>ḥadīṯ</em>s and regenerating the entire reader anew.</p>
<h2 id="in-the-classroom">In the classroom</h2>
<p>In my teaching, I used this reader in combination with ‘micropublications’, which provided each student with a thorough practice of foundational skills necessary for mastering the language: for each <em>ḥadīṯ</em> students provided full vocalization, morphological stemming, and translation aligned with its Arabic original. Such ‘micropublications’ help monitoring students’ progress, and, later, can be used to automatically grade such assignments, thus freeing up time for in-class discussions. Last but not least, by producing these micropublications, students make a valuable contribution as they generate training data that can be used for various teaching and research purposes.</p>

<figure class="fit">
	<a href="../files/Romanov_CATWOP.pdf" title="Download the Reader">
		<img src="../images/fbr/Flyer_Spring2015.jpg">
	</a>
</figure>

<div class="footnotes">
<h2>Footnotes</h2>
<ol>
<li id="fn1"><p>“Classical Arabic through the Words of the Prophet” (Tufts University, Winter/Spring 2015), with the following two additional readings: <span class="citation">W. M. Thackston, <em>An Introduction to Koranic and Classical Arabic: An Elementary Grammar of the Language</em> (Bethesda, Md.: Ibex Publishers, 2000)</span>, <span class="citation">Jonathan Brown, <em>Hadith: Muhammad’s Legacy in the Medieval and Modern World</em> (Oxford: Oneworld, 2009)</span>.<a href="#fnref1">↩</a></p></li>
<li id="fn2"><p>On normalization, see: <span class="citation">Nizar Y. Habash, <em>Introduction to Arabic Natural Language Processing</em> ([San Rafael, Calif.]: Morgan &amp; Claypool Publishers, 2010), 21–23</span>.<a href="#fnref2">↩</a></p></li>
<li id="fn3"><p>For example, Buckwalter Morphological Analyser, which has been tested with this corpus (using Perseus morphological services), returned no results for about 25% of tokens, single results for another 25%, and more than one for the rest 50%. Needless to say, such results are hardly useable for our purposes.<a href="#fnref3">↩</a></p></li>
<li id="fn4"><p>An ability to recognize rare forms is important, of course, but it can be practiced through grammatical and morphological exercises (examples can be found at the end of the reader).<a href="#fnref4">↩</a></p></li>
</ol>
</div>
