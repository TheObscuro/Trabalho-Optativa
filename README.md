# Hub Conecta

SPA educativa para explorar como conteúdos, publicidade e algoritmos podem participar de decisões cotidianas. A interface reúne dois percursos independentes: **“Confiável ou viral?”**, uma auditoria de publicações, e **“Escolha ou influência?”**, uma simulação de feed.

O site foi implementado em `client/index.html`, com HTML, estilos, Tailwind CSS via CDN e JavaScript embutido. Não requer uma API, banco de dados ou autenticação para executar os percursos.

## Executar

### Abrir o arquivo diretamente

Abra `client/index.html` em um navegador moderno. Essa forma segue o requisito de arquivo único e não precisa de Node.js ou etapa de compilação. Como o Tailwind CSS e as fontes são carregados por serviços externos, é necessária conexão à internet para que esses recursos apareçam.

### Usar a prévia de desenvolvimento

Na raiz do projeto, instale as dependências uma vez e inicie o servidor local:

```bash
pnpm install
pnpm dev
```

Para verificar a compilação de produção:

```bash
pnpm build
```

## Percursos

### Tema 1 — Confiável ou viral?

O participante escolhe uma de duas publicações fictícias, registra uma impressão inicial e revela as seis pistas do dossiê. Pode então registrar uma nova decisão e explicar brevemente o que a motivou. O marcador vai de 0 a 6 e acrescenta um ponto por pista aberta. Ele mede apenas a investigação realizada, não a decisão tomada.

O checklist “Antes de compartilhar…” reúne sete itens interativos. O banner **“Popularidade ≠ confiabilidade”** diferencia alcance de evidência.

### Tema 2 — Escolha ou influência?

O participante seleciona um cenário, uma opção e o motivo inicial. Em seguida, explora um feed simulado com exemplos de conteúdo neutro, depoimento de criador, promoção, apelo visual e repetição algorítmica. No fim, registra se manteria ou mudaria a opção e marca os fatores que percebeu.

O painel compara a primeira e a segunda opção e apresenta um score de 0 a 7. Os pontos representam categorias de influência reconhecidas, incluindo a justificativa inicial; não avaliam alimentos nem decisões de consumo. A regra de associação entre fatores e os sete gatilhos está no código do handler `finish-theme2`.

## Princípios pedagógicos

- O conteúdo não prescreve dietas nem classifica alimentos como bons ou ruins.
- As pontuações representam pistas ou fatores percebidos, nunca acertos, falhas ou escolhas de consumo.
- Os estados de auditoria e de feed ficam separados. Alternar ou reiniciar um percurso não transfere o progresso ao outro.
- Os posts e anúncios são simulações educativas. As imagens são ilustrativas e não devem ser interpretadas como comprovação de resultados ou recomendação de produto.

## Estrutura e manutenção

- `client/index.html` — documento principal, telas, estilos, conteúdo e lógica interativa.
- `/manus-storage/skin-example_34ba83b0.jpg` — visual ilustrativo do post de skincare.
- `/manus-storage/feed-example_61b6991f.jpg` — visual ilustrativo do feed.

As imagens usam caminhos do armazenamento gerenciado do projeto. Se o arquivo for levado para fora do WebDev, substitua esses caminhos por arquivos ou URLs acessíveis no novo ambiente.

A navegação global alterna a visibilidade das três telas. Os estados principais estão organizados em `auditState` e `theme2State`. Para acrescentar cenários, atualize os dados em `scenarios`; para alterar as pistas, edite `clueData`. Preserve a separação entre os estados e as regras de neutralidade nutricional ao ampliar o conteúdo.

## Referências

[1]: https://tailwindcss.com/docs/installation/play-cdn "Tailwind CSS Play CDN"
[2]: https://vite.dev/guide/ "Vite — Guide"
