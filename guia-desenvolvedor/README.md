# Guia do Desenvolvedor 1.0
Nesse guia vamos cobrir as principais boas práticas para desenvolvimento de uma aplicação com framework **Angular** e linguagem **TypeScript**. Essa "boas práticas" serão baseadas nas indicações contidas no livro "_Código Limpo_" do _Robert C. Martin (Uncle Bob)_.

## Boas práticas para nomenclatura
Convenções de nomenclatura são extremamente importantes para a manutenção e legibilidade. Este guia recomenda convenções de nomenclatura para o nomes dos arquivos e dos símbolos (_variáveis, classes, funções, etc..._) do projeto.
Manter um sistema é mais complicado do que fazer um do zero. Por isso, é importante ter em mente de que a qualidade do código é importante. Os programadores passam mais tempo lendo código ao invés de escrever, logo, devemos deixa-los fáceis de serem compreendidos por outros programadores.

### Diretrizes gerais de nomenclatura
De acordo com o Uncle Bob, devemos optar pela escolha nomes descritivos e inequívocos. Dessa forma, em aplicações Angular, recomenda-se que siga um padrão que descreva a característica do símbolo e depois o seu tipo. O padrão recomendado é `feature.type.ts`.
