---
title: "Full-waveform Inversion"
excerpt: "Nonelinear Seismic Inversion <br/><img src='/assets/research/FWI-Field-data.png'>"
collection: research
---

 * Develop a unified Full-waveform Inversion platform with features of two and three dimensions, acoustic and elastic medium, and high-performance computing.
   ![image](/assets/research/FWI-model-test.png)

   

  * Apply FWI on the wide-aperture land seismic dataset to reveal crustal structures and investigate the underlying tectonophysics. Study the optimal preprocessing & inversion workflow for field-data FWI applications.
    ![image](/assets/research/FWI-Field-data.png)




under development ...


## Motivations
## Theory of FWI


## Inversion Gallery

   ![image](/assets/research/FWI-model-test.png)

## Field-data Applications

   ![image](/assets/research/FWI-Field-data.png)


## Velocity Models

Below list some useful velocity models for testing the FWI algorithms. More velocity models and open data can be found on the [SEG website](https://wiki.seg.org/wiki/Open_data)

1. **Marmousi2 model**: [link](https://wiki.seg.org/wiki/AGL_Elastic_Marmousi)

   Martin, G. S., 2004, The Marmousi2 model, elastic synthetic data, and an analysis of imaging and AVO in a structurally complex environment: Master’s thesis. University of Houston

   Martin, G. S., Wiley, R., & Marfurt, K. J. (2006). Marmousi2: An elastic upgrade for Marmousi. *The leading edge*, *25*(2), 156-166.

2. **Overthrust model**: [link](https://wiki.seg.org/wiki/SEG/EAGE_Salt_and_Overthrust_Models)

   Aminzadeh, F., Brac, J., Kunz, T., 1997. SEG/EAGE 3-D Salt and Overthrust Models. SEG/EAGE 3-D Modeling Series, No. 1: Distribution CD of Salt and Overthrust models, SEG book series.

3. **SEAE-I model**: [link](https://wiki.seg.org/wiki/SEAM)

   Fehler, M., & Keliher, P. J. (2011). *SEAM Phase 1: Challenges of subsalt imaging in tertiary basins, with emphasis on deepwater Gulf of Mexico*. Society of Exploration Geophysicists.

4. **Foothill model**

   Gray, S. H., & Marfurt, K. J. (1995). Migration from topography: Improving the near-surface image. *Canadian Journal of Exploration Geophysics*, *31*(1-2), 18-24.



## Open Code Collection

<!-- 
* Basic config options: _config.yml
* Top navigation bar config: _data/navigation.yml
* Single pages: _pages/
* Collections of pages are .md or .html files in:
  * _publications/
  * _research/
  * _posts/
  * _code/
  * _talks/
* Footer: _includes/footer.html
* Static files (like PDFs): /files/
* Profile image (can set in _config.yml): images/profile.png



## Locations of key files/directories

* Basic config options: _config.yml
* Top navigation bar config: _data/navigation.yml
* Single pages: _pages/
* Collections of pages are .md or .html files in:
  * _publications/
  * _research/
  * _posts/
  * _code/
  * _talks/
* Footer: _includes/footer.html
* Static files (like PDFs): /files/
* Profile image (can set in _config.yml): images/profile.png

## Tips and hints

* Name a file ".md" to have it render in markdown, name it ".html" to render in HTML.
* Go to the [commit list](https://github.com/academicpages/academicpages.github.io/commits/master) (on your repo) to find the last version Github built with Jekyll. 
  * Green check: successful build
  * Orange circle: building
  * Red X: error
  * No icon: not built

## Resources
 * [Liquid syntax guide](https://shopify.github.io/liquid/tags/control-flow/)

## Markdown guide

### Header three

#### Header four

##### Header five

###### Header six

## Blockquotes

Single line blockquote:

> Quotes are cool.

## Tables

### Table 1

| Entry            | Item   |                                                              |
| --------         | ------ | ------------------------------------------------------------ |
| [John Doe](#)    | 2016   | Description of the item in the list                          |
| [Jane Doe](#)    | 2019   | Description of the item in the list                          |
| [Doe Doe](#)     | 2022   | Description of the item in the list                          |

### Table 2

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|-----------------------------|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=============================|
| Foot1   | Foot2   | Foot3   |

## Definition Lists

Definition List Title
:   Definition list division.

Startup
:   A startup company or startup is a company or temporary organization designed to search for a repeatable and scalable business model.

#dowork
:   Coined by Rob Dyrdek and his personal body guard Christopher "Big Black" Boykins, "Do Work" works as a self motivator, to motivating your friends.

Do It Live
:   I'll let Bill O'Reilly [explain](https://www.youtube.com/watch?v=O_HyZ5aW76c "We'll Do It Live") this one.

## Unordered Lists (Nested)

  * List item one 
      * List item one 
          * List item one
          * List item two
          * List item three
          * List item four
      * List item two
      * List item three
      * List item four
  * List item two
  * List item three
  * List item four

## Ordered List (Nested)

  1. List item one 
      1. List item one 
          1. List item one
          2. List item two
          3. List item three
          4. List item four
      2. List item two
      3. List item three
      4. List item four
  2. List item two
  3. List item three
  4. List item four

## Buttons

Make any link standout more when applying the `.btn` class.

## Notices

**Watch out!** You can also add notices by appending `{: .notice}` to a paragraph.
{: .notice}

## HTML Tags

### Address Tag

<address>
  1 Infinite Loop<br /> Cupertino, CA 95014<br /> United States
</address>

### Anchor Tag (aka. Link)

This is an example of a [link](http://github.com "Github").

### Abbreviation Tag

The abbreviation CSS stands for "Cascading Style Sheets".

*[CSS]: Cascading Style Sheets

### Cite Tag

"Code is poetry." ---<cite>Automattic</cite>

### Code Tag

You will learn later on in these tests that `word-wrap: break-word;` will be your best friend.

### Strike Tag

This tag will let you <strike>strikeout text</strike>.

### Emphasize Tag

The emphasize tag should _italicize_ text.

### Insert Tag

This tag should denote <ins>inserted</ins> text.

### Keyboard Tag

This scarcely known tag emulates <kbd>keyboard text</kbd>, which is usually styled like the `<code>` tag.

### Preformatted Tag

This tag styles large blocks of code.

<pre>
.post-title {
  margin: 0 0 5px;
  font-weight: bold;
  font-size: 38px;
  line-height: 1.2;
  and here's a line of some really, really, really, really long text, just to see how the PRE tag handles it and to find out how it overflows;
}
</pre>

### Quote Tag

<q>Developers, developers, developers&#8230;</q> &#8211;Steve Ballmer

### Strong Tag

This tag shows **bold text**.

### Subscript Tag

Getting our science styling on with H<sub>2</sub>O, which should push the "2" down.

### Superscript Tag

Still sticking with science and Isaac Newton's E = MC<sup>2</sup>, which should lift the 2 up.

### Variable Tag

This allows you to denote <var>variables</var>. -->

