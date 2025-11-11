# FormadoraIII — Projeto de Contatos (Ionic/Angular)

Projeto de exemplo em Ionic + Angular para gerenciar contatos.

## Visão geral
Este projeto é uma aplicação mobile/web (Ionic + Angular) para adicionar, listar, editar e remover contatos. Foi personalizado visualmente com uma paleta moderna, tipografia Poppins e pequenas animações para uma melhor experiência.

Principais pontos:
- Ionic 8 / Angular 20
- Firebase Realtime Database (serviço em `src/app/service/firebase.service.ts`)
- Estilos centralizados em `src/theme/variables.scss` e `src/global.scss`
- Componentes: `contato-item`, páginas `listar-contatos` e `adicionar-contato`


## O que eu (autor das alterações) mudei no visual
- Nova paleta de cores (indigo/teal), tokens de design (borda, espaço, elevação).
- Tipografia: Poppins (importada em `index.html`).
- Cards com bordas arredondadas, sombras suaves e fundo "surface" semi-opaque.
- Inputs padronizados com borda sutil e cor de texto garantida (via `::part(native)`).
- Animações CSS globais (entrada `slideUpFade`, `pop` para pop-in, micro-interações `hover-pulse`).
- Ajustes para garantir que o nome do contato e textos dos inputs tenham contraste legível.

Arquivos principais de estilo:
- `src/theme/variables.scss` — tokens e paleta
- `src/global.scss` — imports, fontes, animações e regras globais
- `src/app/components/contato-item/contato-item.component.scss`
- `src/app/listar-contatos/listar-contatos.page.scss`
- `src/app/adicionar-contato/adicionar-contato.page.scss`


## Requisitos
- Node.js (recomendado 18+)
- npm

## Como rodar (desenvolvimento) — PowerShell (Windows)
Abra o PowerShell na pasta do projeto (`FormadoraIII`) e execute:

```powershell
cd "C:\Users\julia\OneDrive\Documentos\formadora3\FormadoraIII"
npm install
npm run start
# ou
# ionic serve
```

Depois abra o navegador em http://localhost:8100 (ou URL mostrada pela CLI).

## Build para produção
```powershell
cd "C:\Users\julia\OneDrive\Documentos\formadora3\FormadoraIII"
npm run build
```
O build gera os artefatos finais em `www/`.

Para servir rapidamente a pasta `www` localmente (após build):
```powershell
cd "C:\Users\julia\OneDrive\Documentos\formadora3\FormadoraIII"
npm install -g serve # opcional
npx serve www
# ou (se instalou globalmente)
serve www
```

## Scripts importantes (do package.json)
- `npm run start` — inicia o dev server (ionic serve)
- `npm run build` — build de produção
- `npm run test` — executa testes (se configurados)
- `npm run lint` — roda linter (eslint)


## Configuração do Firebase
O projeto usa Firebase Realtime Database. Verifique `src/environments/environment.ts` para informações de configuração. Se não existir, crie um arquivo com as credenciais do seu projeto Firebase antes de rodar operações que acessam o banco.

Exemplo mínimo (não commitar credenciais sensíveis):
```ts
export const environment = {
	firebase: {
		apiKey: "SUA_API_KEY",
		authDomain: "SEU_AUTH_DOMAIN",
		databaseURL: "SUA_DATABASE_URL",
		projectId: "SEU_PROJECT_ID",
		storageBucket: "...",
		messagingSenderId: "...",
		appId: "..."
	}
};
```


## Observações e dicas
- Se o layout parecer estranho, limpe cache do navegador e recarregue; SCSS é recompilado na build.
- O visual foi refeito com tokens — prefira alterar `src/theme/variables.scss` para mudar cores, espaços e sombras de forma centralizada.
- Há um aviso não-bloqueante do Stencil/ionicons durante a build (glob pattern) — não interfere no funcionamento.


## Como contribuir
1. Fork do repositório
2. Crie um branch: `git checkout -b feat/minha-alteracao`
3. Faça alterações e commit: `git commit -am "Descrição"`
4. Abra um pull request explicando as mudanças


## Licença
MIT — sinta-se livre para usar e adaptar.


## Contato
Se quiser que eu refine o tema (toggle dark mode, ajustes de contraste, animações mais suaves ou PR com as mudanças), me diga quais preferências visuais você quer e eu implemento.
