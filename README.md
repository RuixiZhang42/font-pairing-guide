[简体中文](https://github.com/RuixiZhang42/font-pairing-guide)
/
[English](README-EN.md)

# 字体搭配指南

针对中文与西文的混合排版，本指南着重讨论以下三个需要注意的问题：

1. 中西文不同字体之间相对字号大小（relative font size）的调整；
2. 字重（weight）的搭配；
3. 中文汉字与西文字母、数字之间空白间距的设定。

本指南不涉及「哪种西文字体与中文字体搭配起来比较好看」这类「审美」的问题，而是侧重讨论上述三个「技术性」问题。

对于在这里讨论出来的排版思路，我们以「XeLaTeX 排版系统」为例，提供具体的实现方法。

---

<figure>
  <img src="SVG/Example.svg" alt="Example">
  <figcaption>字号：思源宋体&nbsp;Heavy 42&#8239;bp，TeX Gyre Termes&nbsp;Bold 46.41&#8239;bp。<br>
  行距：56&#8239;bp / 行间距：14&#8239;bp。&zwj;[^unit]</figcaption>
</figure>

[^unit]: 在 TeX 中，1&#8239;bp = <sup>1</sup>&frasl;<sub>72</sub>&#8239;in
≈ 0.35278&#8239;mm——即 Adobe 软件与 Microsoft Office 中的「1&nbsp;磅」, 而
1&#8239;pt = <sup>1</sup>&frasl;<sub>72.27</sub>&#8239;in
≈ 0.35146&#8239;mm。

---

## 相对字号大小的调整

我们先来看看下面这段话：

<figure>
  <img src="SVG/Example-1-1.svg" alt="Example 1.1">
  <figcaption>字号：思源宋体&nbsp;Regular 16&#8239;bp，STIX&nbsp;Regular 16&#8239;bp。</figcaption>
</figure>

不难看出，当我们读到「typography」、「τύπος」这些西文单词时，会有一种「西文矮了一截、就像掉下去了」的感觉。为了解决这个「搭配不协调」的问题，我们可以从西文字母的形状出发，探讨解决方法。

<figure>
  <img src="SVG/Example-1-2.svg" alt="Example 1.2">
  <figcaption>西文大小写字母的形状有差异。</figcaption>
</figure>

因为西文的大写字母「等高」与汉字相似，所以我们可以用「**对齐大写字母中线与汉字中线**」作为方向性的指导：

<figure>
  <img src="SVG/Example-1-3.svg" alt="Example 1.3">
  <figcaption>上图：通过上调西文的基线来对齐大写字母与汉字的中线。<br>
  下图：通过放大西文的字号来对齐大写字母与汉字的中线。</figcaption>
</figure>
