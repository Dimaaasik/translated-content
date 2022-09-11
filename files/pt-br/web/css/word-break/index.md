---
title: word-break
slug: Web/CSS/word-break
tags:
  - CSS
  - Propriedade CSS
  - Referencia
translation_of: Web/CSS/word-break
---
<div>{{CSSRef}}</div>

<p>A propriedade CSS <strong><code>word-break</code></strong> é usada para especificar se o navegador deve inserir ou não quebras de linha onde, normalmente, o texto vazaria de seu container.</p>

<div>{{EmbedInteractiveExample("pages/css/word-break.html")}}</div>

<div> </div>

<div class="note">
<p><strong>Nota: </strong>comparando com {{cssxref("overflow-wrap")}}, <code>word-break</code> criará uma quebra de linha no ponto exato em que o texto vazaria, mesmo que uma palavra pudesse ser colocada por completo em uma nova linha sem a necessidade de quebra da palavra.</p>
</div>

<h2 id="Sintaxe">Sintaxe</h2>

<pre class="brush:css">/* Valores específicos */
word-break: normal;
word-break: break-all;
word-break: keep-all;

/* Valores globais */
word-break: inherit;
word-break: initial;
word-break: unset;
</pre>

<h3 id="Valores">Valores</h3>

<dl>
 <dt><code>normal</code></dt>
 <dd>Usa a regra de quebra de linha padrão.</dd>
 <dt><code>break-all</code></dt>
 <dd>Quebras de linha podem ser inseridas entre quaisquer caracteres de texto não-CJC (Chinês/Japonês/Coreano).</dd>
 <dt><code>keep-all</code></dt>
 <dd>Não permite quebra de linha para texto CJC. Texto não-CJC se comporta como <code>normal</code>.</dd>
 <dt><code>break-word</code></dt>
 <dd>Para evitar o vazamento, palavras que normalmente não seriam quebradas podem ser quebradas em pontos arbitrários se não houver pontos de quebra válidos na linha.</dd>
</dl>

<h3 id="Sintaxe_formal">Sintaxe formal</h3>

{{csssyntax}}

<h2 id="Examples" name="Examples">Exemplos</h2>

<h3 id="Conteúdo_HTML">Conteúdo HTML</h3>

<pre class="brush: html line-numbers  language-html"><code class="language-html">&lt;p&gt;1. &lt;code&gt;word-break: normal&lt;/code&gt;&lt;/p&gt;
&lt;p class="normal narrow"&gt;This is a long and
 Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 次の単語グレートブリテンおよび北アイルランド連合王国で本当に大きな言葉&lt;/p&gt;

&lt;p&gt;2. &lt;code&gt;word-break: break-all&lt;/code&gt;&lt;/p&gt;
&lt;p class="breakAll narrow"&gt;This is a long and
 Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 次の単語グレートブリテンおよび北アイルランド連合王国で本当に大きな言葉&lt;/p&gt;

&lt;p&gt;3. &lt;code&gt;word-break: keep-all&lt;/code&gt;&lt;/p&gt;
&lt;p class="keepAll narrow"&gt;This is a long and
 Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 次の単語グレートブリテンおよび北アイルランド連合王国で本当に大きな言葉&lt;/p&gt;

&lt;p&gt;4. &lt;code&gt;word-break: break-word&lt;/code&gt;&lt;/p&gt;
&lt;p class="breakWord narrow"&gt;This is a long and
  Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
  次の単語グレートブリテンおよび北アイルランド連合王国で本当に大きな言葉&lt;/p&gt;</code></pre>

<h3 id="Conteúdo_CSS">Conteúdo CSS</h3>

<pre class="brush: css">.narrow {
    padding: 5px;
    border: 1px solid;
    display: table;
    max-width: 100%;
}

.normal {
    word-break: normal;
}

.breakAll {
    word-break: break-all;
}

.keepAll {
    word-break: keep-all;
}

.breakWord {
    word-break: break-word;
}</pre>

<p>{{ EmbedLiveSample('Examples', '100%', 600) }}</p>

<h2 id="Especificações">Especificações</h2>

<table class="standard-table">
 <thead>
  <tr>
   <th scope="col">Especificação</th>
   <th scope="col">Status</th>
   <th scope="col">Commentário</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>{{SpecName('CSS3 Text', '#word-break-property', 'word-break')}}</td>
   <td>{{Spec2('CSS3 Text')}}</td>
   <td>Definição inicial</td>
  </tr>
 </tbody>
</table>

<h2 id="Browser_compatibility">Compatibilidade com navegadores</h2>

<div>{{Compat("css.properties.word-break")}}</div>

<p> </p>

<h2 id="See_also" name="See_also">Veja também</h2>

<ul>
 <li>{{cssxref("word-wrap")}}</li>
</ul>