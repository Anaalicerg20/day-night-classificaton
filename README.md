Abordagem 1 — Análise da Iluminação por Histograma em Tons de Cinza

A primeira abordagem, considerada a mais eficiente, baseia-se na análise da iluminação da imagem por meio do histograma em tons de cinza. Inicialmente, as imagens são convertidas para escala de cinza, representando apenas a luminância, e em seguida é gerado o histograma de intensidades.

A análise dos histogramas mostrou que imagens diurnas apresentam picos distribuídos ao longo de diversas faixas de intensidade, indicando maior variedade de brilhos. Além disso, essas imagens normalmente apresentam pelo menos um pico relevante em intensidades acima de 127(aproximadamente a metade das intensidades do histograma), o que reflete a presença de regiões bem iluminadas, como céu, nuvens, fachadas claras ou superfícies refletindo luz solar. Já imagens noturnas, mesmo com iluminação artificial, concentram a maior parte dos picos em baixas intensidades, geralmente abaixo de 50, com poucos picos intermediários entre 50 e 127, devido ao predomínio de áreas escuras.

Esse comportamento permitiu uma separação eficaz entre dia e noite, tornando essa abordagem a principal. Contudo, o método pode falhar em imagens noturnas extremamente claras, especialmente quando a iluminação artificial é intensa e capaz de clarear grande parte da cena, fazendo o histograma se assemelhar ao de imagens diurnas.

Abordagem 2 — Análise Cromática da Iluminação Artificial

A segunda abordagem baseia-se na predominância de cores quentes, especialmente tons alaranjados e avermelhados, típicos de iluminação artificial noturna. Para isso, são analisadas razões entre os canais cromáticos, comparando a intensidade média dos canais vermelho e verde em relação ao canal azul.

A razão (R + G)/B mede o quanto os tons quentes dominam a cena em relação aos tons frios. A condição (R+G)/B > 2 indica que a soma das intensidades quentes é pelo menos o dobro da intensidade do canal azul, caracterizando uma dominância significativa de iluminação quente. Adicionalmente, a razão R/B > 1 garante que o canal vermelho participa dessa dominância, evitando classificações incorretas em cenas predominantemente verdes ou cromaticamente neutras.

Imagens que satisfazem simultaneamente essas duas condições são classificadas como noturnas, pois refletem uma assinatura cromática compatível com fontes de luz artificial urbana.

Embora simples, essa abordagem é mais suscetível a erros quando utilizada isoladamente. Ela pode falhar em noites sem iluminação urbana, em cenas noturnas iluminadas por luz branca ou fria, bem como em imagens de nascer e pôr do sol, que naturalmente apresentam tons quentes apesar de ocorrerem durante o dia.

Por esse motivo, essa abordagem não é adequada como critério único, devendo ser utilizada de forma complementar à análise baseada na iluminação global e na distribuição dos níveis de intensidade da imagem.

Uso Complementar das Abordagens

A combinação das duas abordagens permite lidar com casos ambíguos. A classificação deve ser baseada principalmente na distribuição de intensidades do histograma em tons de cinza. Em situações em que a imagem é predominantemente escura, mas apresenta picos em intensidades acima de 127, a análise cromática pode ser utilizada para verificar se esses picos correspondem a iluminação artificial quente, caracterizando uma noite urbana, e não um dia nublado.
