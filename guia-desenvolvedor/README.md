
# Guia do Desenvolvedor 1.0
Nesse guia vamos cobrir as principais boas práticas para desenvolvimento de uma aplicação com framework **Angular** e linguagem **TypeScript**. Essa "boas práticas" serão baseadas nas indicações contidas no livro "_Código Limpo_" do _Robert C. Martin (Uncle Bob)_.

## Responsabilidade única

### Regra do 1 para 1
Declare apenas uma coisa, como serviço, componente, diretiva ou módulo por arquivo. Tente manter cada arquivo com até no máximo 400 linhas. Um componente por arquivo torna muito mais fácil ler, manter e evitar conflitos com equipes no seu VCS.
Exemplo de **má prática** fazer:
```typescript
/* Evitar! */
class Heroi {
  id: number;
  nome: string;
}

@Component({
...
})
class AppComponent implements OnInit {
  title = 'Título';

  herois: Heroi[] = [];

  ngOnInit() {
    getHeroes().then(herois => (this.heroes = herois));
  }
}

@NgModule({
...
})
export class AppModule {}

platformBrowserDynamic().bootstrapModule(AppModule);

const HEROIS: Hero[] = [
  { id: 1, name: 'Batman' },
  { id: 2, name: 'Homem Aranha' },
  { id: 3, name: 'Mulher Maravilha' }
];

function getHerois(): Promise<Heroi[]> {
  return Promise.resolve(HEROIS);
}
```

## Boas práticas para nomenclatura
Convenções de nomenclatura são extremamente importantes para a manutenção e legibilidade. Este guia recomenda convenções de nomenclatura para o nomes dos arquivos e dos símbolos (_variáveis, classes, funções, etc..._) do projeto.
Manter um sistema é mais complicado do que fazer um do zero. Por isso, é importante ter em mente de que a qualidade do código é importante. Os programadores passam mais tempo lendo código ao invés de escrever, logo, devemos deixa-los fáceis de serem compreendidos por outros programadores.

### Diretrizes gerais de nomenclatura
De acordo com o Uncle Bob, devemos optar pela escolha nomes descritivos e inequívocos. Dessa forma, em aplicações Angular, recomenda-se que siga um padrão que descreva a característica do símbolo e depois o seu tipo. O padrão recomendado é `feature.type.ts`.

### Nome dos símbolos e seus arquivos
Utilize nomes consistentes para todos os componentes sistema de acordo com o conceito que eles representam. Use "pascal case" para nomes das classes. Combine o nome do símbolo com o nome do arquivo que o contém.
Lembre-se que o padrão camel case tem o seguinte formato: `camelCase`, enquanto o pascal case tem o seguinte: `PascalCase` iniciando com letra maiúscula. Além disso, adicione o sufixo com o conceito que o símbolo criado representa (Ex.: Component, Directive, Module, Pipe, ou Service).

Exemplos:

| Nome do símbolo                                                          | Arquivo                 |
| ------------------------------------------------------------------------ | ----------------------- |
| <code>@Component({ ... })<br>export class AppComponent { }</code>        | app.component.ts        |
| <code>@Directive({ ... })<br>export class ValidationDirective { }</code> | validation.directive.ts |
| <code>@NgModule({ ... })<br>export class AppModule</code>                | app.module.ts           |
