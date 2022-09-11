---
title: width
slug: Web/CSS/width
tags:
  - CSS
  - CSS Property
  - NeedsBrowserCompatibility
  - NeedsMobileBrowserCompatibility
  - PrecisaDeCompatibilidadeDeNavegador
  - PrecisadeCompatibilidadeMobile
  - Propriedade CSS
  - Reference
  - Referencia
translation_of: Web/CSS/width
---
<div>{{CSSRef}}</div>

<h2 id="Resumo">Resumo</h2>

<p>A propriedade <a href="pt-BR/docs/Web/CSS">CSS</a> <strong>width</strong> determina a largura da área de conteúdo de um elemento. A <a href="/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model#content-area">área de conteúdo</a> fica dentro do preenchimento, da borda, e da margem de um elemento.</p>

<p>As propriedades {{cssxref("min-width")}} e {{cssxref("max-width")}} sobrescrevem o {{cssxref("width")}}.</p>

<p>{{cssinfo}}</p>

<h2 id="Sintaxe">Sintaxe</h2>

<pre class="brush:css">/* Valores de largura - &lt;length&gt; */
width: 300px;
width: 25em;

/* Valores percentuais - &lt;percentage&gt; */
width: 75%;

/* Valores com palavras-chave */
width: 25em border-box;
width: 75% content-box;
width: max-content;
width: min-content;
width: available;
width: fit-content;
width: auto;

/* Valores Globais */
width: inherit;
width: initial;
width: unset;
</pre>

<h3 id="Valores">Valores</h3>

<dl>
 <dt><code>&lt;length&gt;</code></dt>
 <dd>Veja {{cssxref("&lt;length&gt;")}} para possíveis unidades.</dd>
 <dt><code>&lt;percentage&gt;</code></dt>
 <dd>Especificado como {{cssxref("&lt;percentage&gt;")}} da largura do bloco contido. Se a largura do bloco contido depender da largura do elemento, o layout resultante é indefinido.</dd>
 <dt><code>border-box </code>{{experimental_inline}}</dt>
 <dd>Se presente, o precedente {{cssxref("&lt;length&gt;")}} ou {{cssxref("&lt;percentage&gt;")}} é aplicado para o border box do elemento.</dd>
 <dt><code>content-box</code> {{experimental_inline}}</dt>
 <dd>Se presente, o precedente {{cssxref("&lt;length&gt;")}} ou {{cssxref("&lt;percentage&gt;")}} é aplicado para o content box do elemento.</dd>
 <dt><code>auto</code></dt>
 <dd>O navegador irá calcular e selecionar a largura para o elemento específicado.</dd>
 <dt>fill {{experimental_inline}}</dt>
 <dd>Use o fill-available inline size ou fill-available block size, como um modo apropriado de escrita.</dd>
 <dt><code>max-content</code> {{experimental_inline}}</dt>
 <dd>Da largura interna preferível.</dd>
 <dt><code>min-content</code> {{experimental_inline}}</dt>
 <dd>Da largura interna mínina.</dd>
 <dt><code>available</code> {{experimental_inline}}</dt>
 <dd>Do bloco contendo a largura menos a margin horizontal, borda ou preenchimento.</dd>
 <dt><code>fit-content</code> {{experimental_inline}}</dt>
 <dd>A largura:
 <ul>
  <li>do comprimento interno mínimo.</li>
  <li>do menor comprimento interno preferível e da largura disponível.</li>
 </ul>
 </dd>
</dl>

<h3 id="Sintaxe_Formal">Sintaxe Formal</h3>

{{csssyntax}}

<h2 id="Exemplos">Exemplos</h2>

<h3 id="Largura_padrão">Largura padrão</h3>

<pre class="brush:css">p.douradinho {
  background: gold;
}</pre>

<pre class="brush:html">&lt;p class="douradinho"&gt;A comunidade Mozilla produz diversos softwares incríveis.&lt;/p&gt;</pre>

<p>{{EmbedLiveSample('Largura_padrão', '500px', '64px')}}</p>

<h3 id="Pixels_e_ems">Pixels e ems</h3>

<pre class="brush: css">.largura_px {
  width: 200px;
  background-color: red;
  color: white;
  border: 1px solid black;
}

.largura_em {
  width: 20em;
  background-color: white;
  color: red;
  border: 1px solid black;
}
</pre>

<pre class="brush: html">&lt;div class="largura_px"&gt;Largura medida com px&lt;/div&gt;
&lt;div class="largura_em"&gt;Largura medida com em&lt;/div&gt;</pre>

<p>{{EmbedLiveSample('Pixels_e_ems', '500px', '64px')}}</p>

<h3 id="Porcentagem">Porcentagem</h3>

<pre class="brush: css">.porcentagem {
  width: 20%;
  background-color: silver;
  border: 1px solid red;
}</pre>

<pre class="brush: html">&lt;div class="porcentagem"&gt;Largura em porcentagem&lt;/div&gt;</pre>

<p>{{EmbedLiveSample('Porcentagem', '500px', '64px')}}</p>

<h3 id="max-content">max-content</h3>

<pre class="brush:css;">p.maxgreen {
  background: lightgreen;
  width: intrinsic;           /* Safari/WebKit uses a non-standard name */
  width: -moz-max-content;    /* Firefox/Gecko */
  width: -webkit-max-content; /* Chrome */
}</pre>

<pre class="brush:html">&lt;p class="maxgreen"&gt;A comunidade Mozilla produz diversos softwares incríveis.&lt;/p&gt;</pre>

<p>{{EmbedLiveSample('max-content', '500px', '64px')}}</p>

<h3 id="min-content">min-content</h3>

<pre class="brush:css">p.minblue {
  background: lightblue;
  width: -moz-min-content;    /* Firefox */
  width: -webkit-min-content; /* Chrome */
}</pre>

<pre class="brush:html">&lt;p class="minblue"&gt;A comunidade Mozilla produz diversos softwares incríveis.&lt;/p&gt;</pre>

<p>{{EmbedLiveSample('min-content', '500px', '155px')}}</p>

<h2 id="Especificações">Especificações</h2>

<table class="standard-table">
 <thead>
  <tr>
   <th scope="col">Especificação</th>
   <th scope="col">Status</th>
   <th scope="col">Comentários</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>{{SpecName('CSS3 Box', '#the-width-and-height-properties', 'width')}}</td>
   <td>{{Spec2('CSS3 Box')}}</td>
   <td>Adicionadas as palavras-chave <code>max-content</code>, <code>min-content</code>, <code>available</code>, <code>fit-content</code>, <code>border-box</code>, <code>content-box</code></td>
  </tr>
  <tr>
   <td>{{SpecName('CSS3 Transitions', '#animatable-css', 'width')}}</td>
   <td>{{Spec2('CSS3 Transitions')}}</td>
   <td>Lista a largura como animável.</td>
  </tr>
  <tr>
   <td>{{SpecName('CSS2.1', 'visudet.html#the-width-property', 'width')}}</td>
   <td>{{Spec2('CSS2.1')}}</td>
   <td>Determina em qual elemento vai ser aplicado.</td>
  </tr>
  <tr>
   <td>{{SpecName('CSS1', '#width', 'width')}}</td>
   <td>{{Spec2('CSS1')}}</td>
   <td>Definição inicial</td>
  </tr>
  <tr>
   <td>{{SpecName('CSS3 Sizing', '#width-height-keywords', 'width')}}</td>
   <td>{{Spec2('CSS3 Sizing')}}</td>
   <td>Adiciona novas palavras-chave para largura e altura.</td>
  </tr>
 </tbody>
</table>

<h2 id="Browser_compatibility">Compatibilidade com navegadores</h2>

{{Compat("css.properties.width")}}

<h2 id="Veja_também">Veja também</h2>

<ul>
 <li><a href="/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model">box model</a>, {{cssxref("height")}}, {{cssxref("box-sizing")}}, {{cssxref("min-width")}}, {{cssxref("max-width")}}</li>
</ul>