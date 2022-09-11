---
title: Applying color to HTML elements using CSS
slug: Web/CSS/CSS_Colors/Applying_color
translation_of: Web/HTML/Applying_color
original_slug: Web/HTML/Applying_color
---
<div>{{HTMLRef}}</div>

<p>O uso de cores é uma forma fundamental da expressão humana. Crianças experimentam com cores antes mesmo de ter a destreza manual para desenhar. Talvez por isso, a cor é uma das primeiras coisas com a qual as pessoas querem experimentar quando estão aprendendo a desenvolver websites. Com <a href="/en-US/docs/Web/CSS">CSS</a>, há muitas maneiras de acrescentar cor nos seus <a href="/en-US/docs/Web/HTML/Element">elementos HTML</a> para criar exatamente o visual que você quiser. Esse artigo é um preparativo introduzindo cada uma das formas que a cor CSS pode ser usada no HTML.</p>

<p>Felizmente, adicionar cor no seu HTML é muito fácil, e você pode colorir praticamente qualquer coisa.</p>

<p>Vamos passar pela maior parte de tudo que você precisará saber quando usar cor, incluindo uma <a href="#things_that_can_have_color">lista do que pode ser colorido e quais propriedades CSS estão envolvidas</a>, <a href="#how_to_describe_a_color">como descrever uma cor</a>, e como de fato <a href="#using_color">usar cores em folhas de estilo e scripts</a>. Também daremos uma olhada em como <a href="#letting_the_user_picka_color">permitir que o usuário escolha uma cor</a>.</p>

<p>Então, encerraremos o assunto com uma breve discussão de como <a href="#using_color_wisely">usar cores sabiamente</a>: como selecionar cores apropriadas, tendo em mente as necessidades de pessoas com diferentes capacidades visuais.</p>

<h2 id="Coisas_que_podem_ter_cor">Coisas que podem ter cor</h2>

<p>No nível dos elementos, tudo no HTML pode ter uma cor aplicada. Ao invés, vamos pensar nos tipos de coisas que são desenhadas nos elementos, como texto e bordas e assim por diante. Para cada um deles, veremos uma lista das propriedades CSS que aplicam cor neles.</p>

<p>Em um nível fundamental, a propriedade {{cssxref("color")}} define a cor do primeiro plano do conteúdo de um elemento HTML. Já a propriedade {{cssxref("background-color")}} define a cor do plano de fundo de um elemento HTML. Essas propriedades podem ser usadas em praticamente qualquer elemento.</p>

<h3 id="Texto">Texto</h3>

<p>Sempre que um elemento é renderizado, essas propriedades são usadas para determinar a cor do texto, seu plano de fundo, e quaisquer decorações no texto.</p>

<dl>
 <dt>{{cssxref("color")}}</dt>
 <dd>A cor usada para desenhar o texto e quaisquer<a href="/en-US/docs/Learn/CSS/Styling_text/Fundamentals#Font_style_font_weight_text_transform_and_text_decoration"> decorações de texto</a> (como a adição de sublinhados ou tachados e assim por diante).</dd>
 <dt>{{cssxref("background-color")}}</dt>
 <dd>A cor do plano de fundo do texto.</dd>
 <dt>{{cssxref("text-shadow")}}</dt>
 <dd>Configura um efeito de sombra aplicado ao texto. Entre as opções para os aspectos da sombra, está a cor base da sombra (que será então desfocada e mesclada com o plano de fundo, com base nos outros parâmetros). Veja {{SectionOnPage("/en-US/docs/Learn/CSS/Styling_text/Fundamentals", "Sombras projetadas em texto")}} para descobrir mais.</dd>
 <dt>{{cssxref("text-decoration-color")}}</dt>
 <dd>Por padrão, decorações de texto (como sublinhados, tachados, etc) usam a propriedade <code>color</code> para definir suas cores. No entanto, você pode sobrepor esse comportamento e usar uma cor diferente para elas com a propriedade <code>text-decoration-color</code>.</dd>
 <dt>{{cssxref("text-emphasis-color")}}</dt>
 <dd>A cor usada para desenhar símbolos de ênfase adjacentes a cada caractere no texto. Isso é usado primariamente para desenhar texto para idiomas do Leste Asiático. </dd>
 <dt>{{cssxref("caret-color")}}</dt>
 <dd>A cor usada para desenhar o {{Glossary("caret")}} (às vezes referido como o cursor de entrada de texto) dentro do elemento. Isso é útil apenas em elementos editáveis, como {{HTMLElement("input")}} e {{HTMLElement("textarea")}} ou elementos cujo atributo HTML {{htmlattrxref("contenteditable")}} está definido.</dd>
</dl>

<h3 id="Caixas">Caixas</h3>

<p>Todo elemento é uma caixa com algum tipo de conteúdo, e tem um plano de fundo e uma borda em adição a qualquer conteúdo que a caixa possa ter.</p>

<dl>
 <dt><a href="#borders">Borders</a></dt>
 <dd>Veja a seção <a href="#borders">Borders</a> com uma lista das propriedades CSS que você pode usar para configurar as cores das bordas de uma caixa.</dd>
 <dt>{{cssxref("background-color")}}</dt>
 <dd>A cor de plano de fundo para usar em áreas do elemento que não têm conteúdo de primeiro plano.</dd>
 <dt>{{cssxref("column-rule-color")}}</dt>
 <dd>A cor utilizada para desenhar a linha que separa colunas de texto.</dd>
 <dt>{{cssxref("outline-color")}}</dt>
 <dd>A cor utilizada para desenhar um contorno por fora do elemento. Esse contorno é diferente da borda no sentido de que não há um espaço reservado para ele no documento (portanto, pode sobrepor outros conteúdos). Isso é geralmente usado como um indicador de foco, para mostrar qual elemento receberá eventos de input (entrada de informações).</dd>
</dl>

<h3 id="Bordas">Bordas</h3>

<p>Qualquer elemento pode ter uma <a href="/en-US/docs/Learn/CSS/Styling_boxes/Borders">borda</a> desenhada em torno dele. Uma borda básica de elemento é uma linha desenhada em torno dos cantos do conteúdo do elemento. Veja {{SectionOnPage("/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model", "Box properties")}} para aprender sobre a relação entre elementos e suas bordas, e o artigo <a href="/en-US/docs/Learn/CSS/Styling_boxes/Borders">Estilizando bordas usando CSS </a>para descobrir mais sobre como aplicar estilo em bordas.</p>

<p>Você pode usar a propriedade abreviada de {{cssxref("border")}}, que permite configurar tudo sobre a borda de uma só vez (incluindo características que não são a cor, como sua largura, estilo (sólido, tracejado, etc), e assim por diante).</p>

<dl>
 <dt>{{cssxref("border-color")}}</dt>
 <dd>Especifica uma única cor para todos os lados da borda do elemento.</dd>
 <dt>{{cssxref("border-left-color")}}, {{cssxref("border-right-color")}}, {{cssxref("border-top-color")}}, e {{cssxref("border-bottom-color")}}</dt>
 <dd>Permite definir a cor do lado correspondente da borda do elemento.</dd>
 <dt>{{cssxref("border-block-start-color")}} e {{cssxref("border-block-end-color")}}</dt>
 <dd>Com esses, você pode definir a cor usada para desenhar as bordas mais próximas do início e do fim do bloco que essa borda rodeia. Em um modo de escrita da esquerda para a direita (como o português é escrito), o início da borda do bloco é o topo e o final é a base. Isso difere do início e final em linha, que são as bordas esquerda e direita (correspondendo a onde cada linha de texto na caixa começa e termina).</dd>
 <dt>{{cssxref("border-inline-start-color")}} e {{cssxref("border-inline-end-color")}}</dt>
 <dd>Isso permite que você defina cor para as beiradas da borda mais próxima ao início e fim do começo das linhas de texto dentro da caixa. O lado que será definido depende das propriedades {{cssxref("writing-mode")}}, {{cssxref("direction")}}, e {{cssxref("text-orientation")}}, que normalmente (mas não sempre) são usadas para ajustar a direção do texto com base no idioma exibido. Por exemplo, se o texto da caixa está sendo renderizado da direita para a esquerda, então o <code>border-inline-start-color</code> é aplicado ao lado direito da borda.</dd>
</dl>

<h3 id="Outras_formas_de_usar_cor">Outras formas de usar cor</h3>

<p>CSS não é a única tecnologia web que suporta cor. Há tecnologias de gráficos disponíveis na web que também suportam cor. </p>

<dl>
 <dt>A <a href="/en-US/docs/Web/API/Canvas_API">Canvas API</a> HTML</dt>
 <dd>Permite desenhar gráficos 2D rasterizados em um elemento {{HTMLElement("canvas")}}. Veja nosso <a href="/en-US/docs/Web/API/Canvas_API/Tutorial">tutorial Canvas</a> para descobrir mais.</dd>
 <dt><a href="/en-US/docs/Web/SVG">SVG</a> (Scalable Vector Graphics)</dt>
 <dd>Permite desenhar imagens usando comandos que criam formas, padrões e linhas específicas para produzir uma figura. Comandos SVG são formatados como XML, e podem ser embedados diretamente em uma página web ou colocados na página usando o elemento {{HTMLElement("img")}}, como qualquer outro tipo de imagem.</dd>
 <dt><a href="/en-US/docs/Web/API/WebGL_API">WebGL</a></dt>
 <dd>A Web Graphics Library é uma API OpenGL e ES-based para desenhar gráficos 2D e 3D de alta performance na web. Veja<a href="/en-US/docs/Learn/WebGL"> Aprenda WebGL para gráficos 2D e 3D</a> para descobrir mais.</dd>
</dl>

<h2 id="Como_descrever_uma_cor">Como descrever uma cor</h2>

<p>Para representar uma cor no CSS, você precisa encontrar uma forma de traduzir o conceito análogo de "cor" em uma forma digital que um computador possa usar. Isso é normalmente feito decompondo a cor em componentes, como a quantidade de cada grupo de cores primárias que se misturam, ou quão brilhante será a cor. Assim,  há diversas formas de descrever uma cor em CSS. </p>

<p>Para uma discussão mais detalhada sobre cada tipo de valor de cor, veja a referência para a unidade CSS {{cssxref("&lt;color&gt;")}}.</p>

<h3 id="Palavras-chave">Palavras-chave</h3>

<p>Um conjunto de nomes padrão de cores foi definido, permitindo que você use essas palavras-chave em vez de representações numéricas de cores, se você preferir isso e houver uma palavra-chave que represente a exata cor que você quer usar. Palavras-chave de cores incluem as cores primárias e secundárias padrão (como <code>red</code>, <code>blue</code>, ou <code>orange</code>), tons de cinza (de <code>black</code> a <code>white</code>, incluindo cores como <code>darkgray</code> e <code>lightgrey</code>), e uma variedade de outras cores mescladas como <code>lightseagreen</code>, <code>cornflowerblue</code>, e <code>rebeccapurple</code>.</p>

<p>Veja {{SectionOnPage("/en-US/docs/Web/CSS/color_value", "Palavras-chave de cor", "code")}} para uma lista de todas as palavras-chave de cores disponíveis.</p>

<h3 id="Valores_RGB">Valores RGB</h3>

<p>Há três formas de representar uma cor RGB em CSS. </p>

<h4 id="Notação_hexadecimal_em_string">Notação hexadecimal em string</h4>

<p>A notação em string hexadecimal representa uma cor usando dígitos hexadecimais correspondentes a cada um dos componentes da cor (vermelho, verde e azul). Um quarto componente também pode ser incluído: o canal alpha (ou opacidade). Cada componente da cor pode ser representado por um número entre 0 e 255 (0x00 and 0xFF) ou, opcionalmente, por um número entre 0 e 15 (0x0 and 0xF). Todos os componentes <em>devem</em> ser especificados usando o mesmo número de dígitos. Se você usar a notação de um dígito, a cor final é computada usando cada dígito do componente duas vezes; ou seja, <code>"#D"</code> se torna <code>"#DD"</code> quando for desenhado.</p>

<p>Uma cor em notação hexadecimal em string sempre começa com o caractere <code>"#"</code>. Depois, vêm os dígitos hexadecimais do código da cor. A string não diferencia maiúsculas de minúsculas.</p>

<dl>
 <dt><code>"#rrggbb"</code></dt>
 <dd>Especifica uma cor totalmente opaca cujo componente vermelho é o número hexadecimal <code>0xrr</code>, o componente verde é <code>0xgg</code>, e o componente azul é <code>0xbb</code>.</dd>
 <dt><code>"#rrggbbaa"</code></dt>
 <dd>Especifica uma cor cujo componente vermelho é o número hexadecimal <code>0xrr</code>, o componente verde é <code>0xgg</code>, e o componente azul é <code>0xbb</code>. O canal alpha é especificado por <code>0xaa</code>; quanto mais baixo o seu valor, mais translúcida a cor se torna.</dd>
 <dt><code>"#rgb"</code></dt>
 <dd>Specifies a color whose red component is the hexadecimal number <code>0xrr</code>, green component is <code>0xgg</code>, and blue component is <code>0xbb</code>.</dd>
 <dt><code>"#rgba"</code></dt>
 <dd>Especifica uma cor cujo componente vermelho é o número hexadecimal <code>0xrr</code>, o componente verde é <code>0xgg</code>, e o componente azul é <code>0xbb</code>. O canal alpha é especificado por <code>0xaa</code>; quanto mais baixo o seu valor, mais translúcida a cor se torna.</dd>
</dl>

<p>Por exemplo, você pode representar a cor opaca azul vibrante como <code>"#0000ff"</code> ou <code>"#00f"</code>. Para torná-lo 25% opaco, você pode usar <code>"#0000ff44"</code> ou <code>"#00f4"</code>.</p>

<h4 id="Notação_funcional_RGB">Notação funcional RGB</h4>

<p>A notação funcional RGB (Red/Green/Blue), como a notação em string hexadecimal, representa cores usando seus componentes vermelho, verde e azul (assim como, opcionalmente, um componente de canal alpha para opacidade). No entanto, ao invés de usar uma string, a cor é definida usando a função CSS {{cssxref("rgb()")}}. Essa função aceita como parâmetros de entrada os valores dos componentes vermelho, verde e azul e um quarto parâmetro opcional, o valor do canal alpha.</p>

<p>Valores válidos para cada um desses parâmetros são:</p>

<dl>
 <dt><code>red</code>, <code>green</code>, e <code>blue</code></dt>
 <dd>Cada um deve ser um valor {{cssxref("&lt;integer&gt;")}} (inteiro) entre 0 e 255 (incluso), ou uma {{cssxref("&lt;percentage&gt;")}} (porcentagem) de 0% a 100%.</dd>
 <dt><code>alpha</code></dt>
 <dd>O canal alpha é um número entre 0.0 (totalmente transparente) e 1.0 (totalmente opaco). Você pode também especificar uma porcentagem onde 0% é o mesmo que 0.0 e 100% é o mesmo que 1.0.</dd>
</dl>

<p>Por exemplo, um vermelho vivo que é 50% opaco pode ser representado como <code>rgb(255, 0, 0, 0.5)</code> ou <code>rgb(100%, 0, 0, 50%)</code>.</p>

<h3 id="Notação_funcional_HSL">Notação funcional HSL </h3>

<p>Designers e artistas frequentemente preferem trabalhar usando o método de cor {{interwiki("wikipedia", "HSL and HSV", "HSL")}} (Hue/Saturation/Luminosity, tradução: "Matiz/Saturação/Luminosidade"). Na web, cores HSL são representadas usando notação funcional HSL. O uso da função CSS <code>hsl()</code> é muito similar ao da função <code>rgb().</code></p>

<img alt="HSL color cylinder" src="https://mdn.mozillademos.org/files/15445/1200px-HSL_color_solid_cylinder_alpha_lowgamma.png" style="height: 375px; width: 500px;">
<em><strong>Um cilindro de cor HSL.</strong> Hue (matiz) define a cor em si, com base na sua posição ao longo de um círculo que representa as cores do espectro visível. Saturation (saturação) é uma porcentagem que representa sua posição no caminho entre ser um tom de cinza ou ter a maior quantidade possível da matiz dada. Conforme o valor de Luminance ou Lightness (luminosidade) aumenta, a cor transiciona do mais escura possível até o mais clara possível (do preto ao branco). Imagem cortesia do usuário <a href="http://commons.wikimedia.org/wiki/User:SharkD">SharkD</a> na <a href="https://www.wikipedia.org/">Wikipedia</a>, distribuída sob a licença <a href="http://creativecommons.org/licenses/by-sa/3.0">CC BY-SA 3.0</a>.</em>

<p>O valor do componente hue/matriz (H) de uma cor HSL é um ângulo partindo do vermelho e passando em círculo pelo amarelo, verde, ciano, azul e magenta (terminando de volta no vermelho em 360°) que identifica qual é a cor base. O valor pode ser especificado em qualquer unidade de {{cssxref("&lt;angle&gt;")}} (ângulo) suportada por CSS, incluindo graus (<code>deg</code>, de "degrees"), radianos (<code>rad</code>, de "radians"), grados (<code>grad</code>, de "gradians") ou revoluções (<code>turn</code>, de "turns"). Mas isso não controla quão vívida ou apagada, ou quão clara ou escura a cor é. </p>

<p>O componente saturation/saturação (S) da cor especifica qual porcentagem da cor final é composta pela matiz especificada. O restante é definido pelo nível de cinza fornecido pelo componente luminance/luminosidade (L). </p>

<p>Pense como se você fosse criar a cor perfeita de tinta:</p>

<ol>
 <li>Você começa com uma tinta de base que tenha a intensidade máxima possível de uma cor dada, como o azul mais intenso que pode ser representado pela tela do usuário. Esse é o componente hue/matiz (H): um valor que representa o ângulo no círculo de cor para a matiz vívida que queremos usar como base.</li>
 <li>Então, seleciona uma tinta na escala de cinza que corresponde a quão clara você quer que a cor seja; essa é a luminance/luminosidade (L). Você quer que seja muito clara e quase branca, ou muito escura e perto do preto, ou algo no meio do caminho? Isso é especificado usando uma porcentagem, onde 0% é perfeitamente preto e 100% é perfeitamente branco (independente da saturação ou matiz). Os valores no meio são a área cinza.</li>
 <li>Agora que você tem uma tinta cinza e uma cor perfeitamente vívida, você precisa misturar as duas. O componente saturation/saturação (S) da cor indica qual porcentagem da cor final deve ser composta dessa cor perfeitamente vívida. O resto da cor final é feito da tinta cinza que representa a saturação. </li>
</ol>

<p>Você também pode opcionalmente incluir um canal alpha, para tornar a cor menos que 100% opaca.</p>

<p>Aqui estão alguns exemplos de cores na notação HSL: </p>

<div id="hsl-swatches">
<div class="hidden">
<pre class="brush: css">table {
  border: 1px solid black;
  font: 16px "Open Sans", Helvetica, Arial, sans-serif;
  border-spacing: 0;
  border-collapse: collapse;
}

th, td {
  border: 1px solid black;
  padding:4px 6px;
  text-align: left;
}

th {
  background-color: hsl(0, 0%, 75%);
}</pre>

<pre class="brush: html">&lt;table&gt;
 &lt;thead&gt;
  &lt;tr&gt;
   &lt;th scope="col"&gt;Color in HSL notation&lt;/th&gt;
   &lt;th scope="col"&gt;Example&lt;/th&gt;
  &lt;/tr&gt;
 &lt;/thead&gt;
 &lt;tbody&gt;
  &lt;tr&gt;
   &lt;td&gt;&lt;code&gt;hsl(90deg, 100%, 50%)&lt;/code&gt;&lt;/td&gt;
   &lt;td style="background-color: hsl(90deg, 100%, 50%);"&gt;&amp;nbsp;&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;&lt;code&gt;hsl(90, 100%, 50%)&lt;/code&gt;&lt;/td&gt;
   &lt;td style="background-color: hsl(90, 100%, 50%);"&gt;&amp;nbsp;&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;&lt;code&gt;hsl(0.15turn, 50%, 75%)&lt;/code&gt;&lt;/td&gt;
   &lt;td style="background-color: hsl(0.15turn, 50%, 75%);"&gt;&amp;nbsp;&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;&lt;code&gt;hsl(0.15turn, 90%, 75%)&lt;/code&gt;&lt;/td&gt;
   &lt;td style="background-color: hsl(0.15turn, 90%, 75%);"&gt;&amp;nbsp;&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;&lt;code&gt;hsl(0.15turn, 90%, 50%)&lt;/code&gt;&lt;/td&gt;
   &lt;td style="background-color: hsl(0.15turn, 90%, 50%);"&gt;&amp;nbsp;&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;&lt;code&gt;hsl(270deg, 90%, 50%)&lt;/code&gt;&lt;/td&gt;
   &lt;td style="background-color: hsl(270deg, 90%, 50%);"&gt;&amp;nbsp;&lt;/td&gt;
  &lt;/tr&gt;
 &lt;/tbody&gt;
&lt;/table&gt;</pre>
</div>

<p>{{EmbedLiveSample("hsl-swatches", 300, 260)}}</p>
</div>

<div class="note">
<p>Note que quando você omite a unidade de medida da matiz, é considerado que ela está em graus/degrees (<code>deg</code>).</p>
</div>

<h2 id="Usando_cor">Usando cor</h2>

<p>Agora que você sabe quais propriedades CSS existentes permitem que você aplique cor a elementos, e quais formatos pode usar para descrever cores, você pode unir ambos para começar a fazer uso delas. Como você pode ter visto na lista em <a href="#things_that_can_have_color">Things that can have color</a>, há muitas coisas que podem ser coloridas com CSS. Vejamos este tema por dois lados: usando cor dentro de uma {{Glossary("stylesheet")}}, e adicionando e mudando cor usando código {{Glossary("JavaScript")}} para alterar os estilos dos elementos.</p>

<h3 id="Especificando_cores_em_folhas_de_estilo">Especificando cores em folhas de estilo</h3>

<p>A forma mais fácil de aplicar cor a elementos—e a forma que você normalmente fará isso—é simplesmente especificar as cores no CSS que será utilizado para renderizar os elementos. Embora não usaremos cada uma das propriedades mencionadas anteriormente, veremos alguns exemplos. O conceito é o mesmo, onde quer que você aplique a cor.</p>

<p>Vejamos um exemplo, começando por analisar os resultados que queremos atingir: </p>

<div>{{EmbedLiveSample("Specifying_colors_in_stylesheets", 650, 150)}}</div>

<h4 id="HTML">HTML</h4>

<p>O HTML responsável por criar o exemplo acima é mostrado aqui:</p>

<pre class="brush: html">&lt;div class="wrapper"&gt;
  &lt;div class="box boxLeft"&gt;
    &lt;p&gt;
      This is the first box.
    &lt;/p&gt;
  &lt;/div&gt;
  &lt;div class="box boxRight"&gt;
    &lt;p&gt;
      This is the second box.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;</pre>

<p>Esse exemplo é bastante simples, usando uma {{HTMLElement("div")}} para envolver o conteúdo, que consiste de mais duas <code>&lt;div&gt;</code>s, cada uma estilizada diferentemente com um único parágrafo ({{HTMLElement("p")}}) em cada caixa.</p>

<p>A mágica acontece, como sempre, no CSS; onde aplicamos a cor definirá o layout para o HTML acima.</p>

<h4 id="CSS">CSS</h4>

<p>Vejamos o CSS para criar os resultados acima, uma parte por vez, para que possamos revisar as partes interessantes uma a uma.</p>

<pre class="brush: css">.wrapper {
  width: 620px;
  height: 110px;
  margin: 0;
  padding: 10px;
  border: 6px solid mediumturquoise;
}</pre>

<p>A classe <code>.wrapper</code> é usada para designar estilos à {{HTMLElement("div")}} que envolve todo o resto do nosso conteúdo. Isso estabelece o tamanho do container usando {{cssxref("width")}} e {{cssxref("height")}}, bem como sua {{cssxref("margin")}} e {{cssxref("padding")}}.</p>

<p>Mais interessante para nossa discussão aqui é o uso da propriedade {{cssxref("border")}} para estabelecer uma borda em torno dos limites externos do elemento. Essa borda é uma linha sólida, com 6 pixels de largura, na cor <code>mediumturquoise</code>.</p>

<p>Nossas duas caixas coloridas compartilham algumas propriedades em comum, então agora estabelecemos uma classe, <code>.box</code>, que define essas propriedades compartilhadas:</p>

<pre class="brush: css">.box {
  width: 290px;
  height: 100px;
  margin: 0;
  padding: 4px 6px;
  font: 28px "Marker Felt", "Zapfino", cursive;
  display: flex;
  justify-content: center;
  align-items: center;
}</pre>

<p>Em suma, <code>.box</code> estabelece o tamanho de cada caixa, assim como a configuração da fonte usada dentro dela. Também tiramos proveito de <a href="/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout">CSS Flexbox</a> para centralizar facilmente os conteúdos de cada caixa. Nós habilitamos o modo <code>flex</code> usando {{cssxref("display", "display: flex")}}, e definimos {{cssxref("justify-content")}} e {{cssxref("align-items")}} como <code>center</code>. Então, podemos criar uma classe para cada uma das duas caixas que defina as propriedades que as diferem.</p>

<pre class="brush: css">.boxLeft {
  float: left;
  background-color: rgb(245, 130, 130);
  outline: 2px solid darkred;
}</pre>

<p><code>A classe .boxLeft</code>—que, apropriadamente, é usada para estilizar a caixa na esquerda—flutua a caixa para a esquerda, e então configura as cores:</p>

<ul>
 <li>A cor de fundo da caixa é definida mudando o valor da propriedade CSS {{cssxref("background-color")}} para <code>rgb(245, 130, 130)</code>.</li>
 <li>Um contorno é definido para a caixa. Diferente da mais comumente utilizada <code>border</code>, {{cssxref("outline")}} não afeta o layout em nada; apenas desenha sobre qualquer coisa que esteja fora da caixa do elemento, em vez de abrir espaço como a <code>border</code> faz. Esse contorno é uma linha vermelha escura sólida que tem dois pixels de espessura. Note o uso da palavra-chave <code>darkred</code> ao especificar a cor.</li>
 <li>Note que não estamos explicitamente definindo a cor do texto. Isso significa que o valor de {{cssxref("color")}} será herdado do elemento-pai mais próximo que a defina. Por padrão, essa cor é preta. </li>
</ul>

<pre class="brush: css">.boxRight {
  float: right;
  background-color: hsl(270deg, 50%, 75%);
  outline: 4px dashed rgb(110, 20, 120);
  color: hsl(0deg, 100%, 100%);
  text-decoration: underline wavy #88ff88;
  text-shadow: 2px 2px 3px black;
}</pre>

<p>Finalmente, a classe <code>.boxRight</code> descreve as propriedades únicas da caixa que está à direita. A caixa está definida para flutuar à direita, de modo que apareça ao lado da caixa anterior. Então, as seguintes cores são estabelecidas: </p>

<ul>
 <li>A <code>background-color</code> é definida usando o valor HSL especificado com <code>hsl(270deg, 50%, 75%)</code>. É um tom de roxo médio.</li>
 <li>O <code>outline</code> da caixa é usado para especificar que a caixa deve ser envolvida em uma linha tracejada de quatro pixels de espessura cuja cor é um roxo um pouco mais escuro (<code>rgb(110, 20, 120)</code>).</li>
 <li>A cor de primeiro plano (texto) é especificada definindo a propriedade {{cssxref("color")}} para <code>hsl(0deg, 100%, 100%)</code>. Essa é uma das muitas formas de especificar a cor branca. </li>
 <li>Acrescentamos uma linha ondulada verde sob o texto com {{cssxref("text-decoration")}}.</li>
 <li>Finalmente, um pouco de sombra é acrescentado ao texto usando {{cssxref("text-shadow")}}. Seu parâmetro <code>color</code> é definido como <code>black</code>.</li>
</ul>

<h2 id="Permitindo_que_o_usuário_escolha_uma_cor">Permitindo que o usuário escolha uma cor</h2>

<p>Há muitas situações em que o seu website pode precisar permitir que o usuário selecione uma cor. Talvez você tenha uma interface de usuário customizável, ou você está implementando um app de desenho. Talvez você tenha texto editável e precise deixar o usuário escolher a cor do texto. Ou talvez seu app permita que o usuário defina cores para pastas ou itens. Apesar de historicamente ter sido necessário implementar o seu próprio {{interwiki("wikipedia", "color picker")}}, o HTML agora suporta que os navegadores forneçam um seletor de cor para seu uso através do elemento {{HTMLElement("input")}}, usando <code>"color"</code> como o valor do seu atributo  {{htmlattrxref("type", "input")}}.</p>

<p>O elemento <code>&lt;input&gt;</code> representa uma cor apenas na <a href="#hexadecimal_string_notation">notação hexadecimal em string</a> explicada acima.</p>

<h3 id="Exemplo_Selecionando_uma_cor">Exemplo: Selecionando uma cor</h3>

<p>Vamos observar um exemplo simples em que o usuário pode escolher uma cor. Conforme o usuário ajusta a cor, a borda em torno do exemplo muda para refletir a nova cor. Depois de terminar e escolher a cor final, o valor do seletor de cor é exibido. </p>

<p>{{EmbedLiveSample("Example_Picking_a_color", 525, 275)}}</p>

<div class="note">
<p>No macOS, você indica que finalizou a seleção da cor fechando a janela do seletor de cor.</p>
</div>

<h4 id="HTML_2">HTML</h4>

<p>O HTML aqui cria uma caixa que contém um controle do seletor de cor (com um rótulo criado usando o elemento {{HTMLElement("label")}}) e um elemento de parágrafo vazio ({{HTMLElement("p")}}) no qual será emitido um texto do nosso código JavaScript. </p>

<pre class="brush: html">&lt;div id="box"&gt;
  &lt;label for="colorPicker"&gt;Border color:&lt;/label&gt;
  &lt;input type="color" value="#8888ff" id="colorPicker"&gt;
  &lt;p id="output"&gt;&lt;/p&gt;
&lt;/div&gt;</pre>

<h4 id="CSS_2">CSS</h4>

<p>O CSS simplesmente estabelece um tamanho para a caixa e alguns estilos básicos para aparência. A borda também é estabelecida com 2 pixels de largura e uma cor que não vai permanecer, cortesia do JavaScript abaixo...</p>

<pre class="brush: css">#box {
  width: 500px;
  height: 200px;
  border: 2px solid rgb(245, 220, 225);
  padding: 4px 6px;
  font: 16px "Lucida Grande", "Helvetica", "Arial", "sans-serif"
}</pre>

<h4 id="JavaScript">JavaScript</h4>

<p>O script aqui faz a tarefa de atualizar a cor inicial da borda para refletir o valor do seletor de cor. Então, dois event handlers são adicionados para lidar com o input do elemento <code><a href="/en-US/docs/Web/HTML/Element/input/color">&lt;input type="color"&gt;</a></code>.</p>

<pre class="brush: js">let colorPicker = document.getElementById("colorPicker");
let box = document.getElementById("box");
let output = document.getElementById("output");

box.style.borderColor = colorPicker.value;

colorPicker.addEventListener("input", function(event) {
  box.style.borderColor = event.target.value;
}, false);

colorPicker.addEventListener("change", function(event) {
  output.innerText = "Color set to " + colorPicker.value + ".";
}, false);</pre>

<p>O evento {{event("input")}} é enviado cada vez que o valor do elemento muda; isto é, cada vez que o usuário ajusta a cor no seletor. Cada vez que esse evento chega, nós configuramos a cor da borda da caixa para refletir o valor atual do seletor de cor. </p>

<p>O evento {{event("change")}} é recebido quando o valor do seletor de cor é finalizado. Nós respondemos mudando o conteúdo do elemento <code>&lt;p&gt;</code> com o ID <code>"output"</code> para uma string que descreve a cor finalmente selecionada.</p>

<h2 id="Usando_cor_com_sabedoria">Usando cor com sabedoria</h2>

<p>Fazer as escolhas certas ao selecionar cores ao criar um website pode ser um processo complicado, especialmente se você não tem uma boa base em arte, design ou pelo menos teoria básica da cor. A escolha incorreta de cor pode tornar seu site pouco atraente, ou pior, deixar o conteúdo ilegível devido a problemas com contraste ou cores conflitantes. Pior ainda, usar as cores incorretas pode tornar seu conteúdo completamente inutilizável por pessoas com certos problemas de visão, especialmente daltonismo. </p>

<h3 id="Encontrando_as_cores_certas">Encontrando as cores certas</h3>

<p>Pensar nas cores corretas pode ser complicado, especialmente sem treinamento em arte ou design. Felizmente, há ferramentas disponíveis que podem te ajudar. Elas não podem substituir a ajuda de um bom designer para tomar essas decisões, mas podem definitivamente te ajudar a começar. </p>

<h4 id="Cor_de_base">Cor de base</h4>

<p>O primeiro passo é escolher sua<strong> cor de base</strong>. Essa é a cor que de certa forma define seu website ou o assunto do site. Da mesma forma que associamos verde com a bebida {{interwiki("wikipedia", "Mountain Dew")}} e podemos relacionar a cor azul com o céu ou oceano, escolher uma cor base apropriada para representar seu site é um bom lugar para começar. Há muitas formas de selecionar uma cor base; algumas idéias incluem: </p>

<ul>
 <li>A color that is naturally associated with the topic of your content, such as the existing color identified with a product or idea or a color representative of the emotion you wish to convey.</li>
 <li>A color that comes from imagery associated with what your content is about. If you're creating a web site about a given item or product, choose a color that's physically present on that item.</li>
 <li>Browse web sites that let you look at lots of existing color palettes and imags to find inspiration.</li>
</ul>

<p>When trying to decide upon a base color, you may find that browser extensions that let you select colors from web content can be particularly handy. Some of these are even specifically designed to help with this sort of work. For example, the web site <a href="http://www.colorzilla.com/">ColorZilla</a> offers an extension (<a href="http://www.colorzilla.com/chrome">Chrome</a> / <a href="http://www.colorzilla.com/firefox">Firefox</a>) that offers an eyedropper tool for picking colors from the web. It can also take averages of the colors of pixels in various sized areas or even a selected area of the page.</p>

<div class="note">
<p>The advantage to averaging colors can be that often what looks like a solid color is actually a surprisingly varied number of related colors all used in concert, blending to create a desired effect. Picking just one of these pixels can result in getting a color that on its own looks very out of place.</p>
</div>

<h4 id="Fleshing_out_the_palette">Fleshing out the palette</h4>

<p>Once you have decided on your base color, there are plenty of online tools that can help you build out a palette of appropriate colors to use along with your base color by applying color theory to your base color to determine appropriate added colors. Many of these tools also support viewing the colors filtered so you can see what they would look like to people with various forms of color blindness. See <a href="#color_and_accessibility">Color and accessibility</a> for a brief explanation of why this matters.</p>

<p>A few examples (all free to use as of the time this list was last revised):</p>

<ul>
 <li><a href="/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool">MDN's color picker tool</a></li>
 <li><a href="http://paletton.com">Paletton</a></li>
 <li><a href="https://color.adobe.com/create/color-wheel">Adobe Color CC online color wheel</a></li>
</ul>

<p>When designing your palette, be sure to keep in mind that in addition to the colors these tools typically generate, you'll probably also need to add some core neutral colors such as white (or nearly white), black (or nearly black), and some number of shades of gray.</p>

<div class="note">
<p>Usually, you are far better off using the smallest number of colors possible. By using color to accentuate rather than adding color to everything on the page, you keep your content easy to read and the colors you do use have far more impact.</p>
</div>

<h3 id="Color_theory_resources">Color theory resources</h3>

<p>A full review of color theory is beyond the scope of this article, but there are plenty of articles about color theory available, as well as courses you can find at nearby schools and universities. A couple of useful resources about color theory:</p>

<dl>
 <dt><a href="https://www.khanacademy.org/partner-content/pixar/color">Color Science</a> (<a href="https://www.khanacademy.org/">Khan Academy</a> in association with <a href="https://www.pixar.com/">Pixar</a>)</dt>
 <dd>An online course which introduces concepts such as what color is, how it's percieved, and how to use colors to express ideas. Presented by Pixar artists and designers.</dd>
 <dt>{{interwiki("wikipedia", "Color theory")}} on Wikipedia</dt>
 <dd>Wikipedia's entry on color theory, which has a lot of great information from a technical perspective. It's not really a resource for helping you with the color sleection process, but is still full of useful information.</dd>
</dl>

<h3 id="Color_and_accessibility">Color and accessibility</h3>

<p>There are several ways color can be an {{Glossary("accessibility")}} problem. Improper or careless use of color can result in a web site or app that a percentage of your target audience may not be able to use adequately, resulting in lost traffic, lost business, and possibly even a public relations problem. So it's important to consider your use of color carefully.</p>

<p>You should do at least basic research into {{interwiki("wikipedia", "color blindness")}}. There are several kinds; the most common is red-green color blindness, which causes people to be unable to differentiate between the colors red and green. There are others, too, ranging from inabilities to tell the difference between certain colors to total inability to see color at all.</p>

<div class="note">
<p>The most important rule: never use color as the only way to know something. If, for example, you indicate success or failure of an operation by changing the color of a shape from white to green for success and red for failure, users with red-green color-blindness won't be able to use your site properly. Instead, perhaps use both text and color together, so that everyone can understand what's happening.</p>
</div>

<p>For more information about color blindness, see the following articles:</p>

<ul>
 <li><a href="https://medlineplus.gov/colorblindness.html">Medline Plus: Color Blindness</a> (United States National Institute of Health)</li>
 <li><a href="https://www.aao.org/eye-health/diseases/what-is-color-blindness">American Academy of Ophthamology: What Is Color Blindness?</a></li>
 <li><a href="https://www.usability.gov/get-involved/blog/2010/02/color-blindness.html">Color Blindness &amp; Web Design</a> (Usability.gov: United States Department of Health and Human Services)</li>
</ul>

<h3 id="Palette_design_example">Palette design example</h3>

<p>Let's consider a quick example of selecting an appropriate color palette for a site. Imagine that you're building a web site for a new game that takes place on the planet Mars. So let's do a <a href="https://www.google.com/search?q=Mars&amp;tbm=isch">Google search for photos of Mars</a>. Lots of good examples of Martian coloration there. We carefully avoid the mockups and the photos from movies. And we decide to use a photo taken by one of the Mars landers humanity has parked on the surface over the last few decades, since the game takes place on the planet's surface. We use a color picker tool to select a sample of the color we choose.</p>

<p>Using an eyedropper tool, we identify a color we like and determine that the color in question is <code>#D79C7A</code>, which is an appropriate rusty orange-red color that's so stereotypical of the Martian surface.</p>

<p>Having selected our base color, we need to build out our palette. We decide to use <a href="http://www.paletteon.com/">Paletteon</a> to come up with the other colors we need. Upon opening Paletton, we see:</p>

<p><img alt="Right after loading Paletton." src="https://mdn.mozillademos.org/files/15451/paletton1.png" style="height: 361px; width: 600px;"></p>

<p>Next, we enter our color's hex code (<code>D79C7A</code>) into the "Base RGB" box at the bottom-left corner of the tool:</p>

<p><img alt="After entering base color" src="https://mdn.mozillademos.org/files/15453/paletton2.png" style="height: 361px; width: 600px;"></p>

<p>We now see a monochromatic palette based on the color we picked from the Mars photo. If you need a lot of related colors for some reason, those are likely to be good ones. But what we really want is an accent color. Something that will pop along side the base color. To find that, we click the "add complementary" toggle underneath the menu that lets you select the palette type (currently "Monochromatic"). Paletton computes an appropriate accent color; clicking on the accent color down in the bottom-right corner tells us that this color is <code>#508D7C</code>.</p>

<p><img alt="Now with complementary colors included." src="https://mdn.mozillademos.org/files/15455/paletton3.png" style="height: 361px; width: 600px;"></p>

<p>If you're unhappy with the color that's proposed to you, you can change the color scheme, to see if you find something you like better. For example, if we don't like the proposed greenish-blue color, we can click the Triad color scheme icon, which presents us with the following:</p>

<p><img alt="Triad color scheme selected" src="https://mdn.mozillademos.org/files/15457/paletton4.png" style="height: 361px; width: 600px;"></p>

<p>That greyish blue in the top-right looks pretty good. Clicking on it, we find that it's <code>#556E8D</code>. That would be used as the accent color, to be used sparingly to make things stand out, such as in headlines or in the highlighting of tabs or other indicators on the site:</p>

<p><img alt="Triad color scheme selected" src="https://mdn.mozillademos.org/files/15459/paletton-color-detail.png" style="height: 370px; width: 526px;"></p>

<p>Now we have our base color and our accent. On top of that, we have a few complementary shades of each, just in case we need them for gradients and the like. The colors can then be exported in a number of formats so you can make use of them.</p>

<p>Once you have these colors, you will probably still need to select appropriate neutral colors. Common design practice is to try to find the sweet spot where there's just enough contrast that the text is crisp and readable but not enough contrast to become harsh for the eyes. It's easy to go too far in one way or another so be sure to get feedback on your colors once you've selected them and have examples of them in use available. If the contrast is too low, your text will tend to be washed out by the background, leaving it unreadable, but if your contrast is too high, the user may find your site garish and unpleasant to look at.</p>

<h2 id="See_also">See also</h2>

<ul>
 <li><a href="/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Drawing_graphics">Drawing graphics</a></li>
 <li><a href="/en-US/docs/Web/Guide/Graphics">Graphics on the web</a></li>
 <li><a href="/en-US/docs/Tools/DevToolsColors">MDN's color picker tool</a></li>
</ul>