# IFL URL PVD (Redirect Technology)

Mecanismo simples de redirecionamento com base em parâmetros codificados na URL. Recebe dados via query string, interpreta no navegador e executa ações (ex.: envio para WhatsApp) conforme regras definidas.

## Menu
### Gerador de URL de Redirecionamento
[acesso à ferramenta](https://ifl-co.github.io/redir/gen.html)
`https://ifl-co.github.io/redir/gen.html`

<a href="https://ifl-co.github.io/redir/gen.html" target="_blank" rel="noopener noreferrer">acesso à ferramenta</a>

---

## Como funciona

1. A URL contém um parâmetro `data` em Base64:

/redir/redirect.html?data=BASE64

2. O conteúdo decodificado segue o padrão:

dominio.com.br:2500

- dominio: ativo negociado  
- 2500: valor mínimo

3. O script:

- decodifica o Base64  
- separa os dados (:)  
- aplica a regra:
  - valor ≥ mínimo → segue fluxo (ex.: WhatsApp)
  - valor < mínimo → bloqueia e exibe aviso

---

## Exemplo

Gerar payload:

echo -n "dominio.com.br:2500" | base64

URL final:

/redir/redirect.html?data=ZG9taW5pby5jb20uYnI6MjUwMA==

---

## Estrutura

/redir
 ├── redirect.html
 └── query.html

---

## Personalização

- editar mensagens e layout em redirect.html  
- ajustar regras em query.html  
- alterar destino (WhatsApp ou outro endpoint)

---

## Observação

Validação ocorre no frontend. Para maior segurança, recomenda-se validação adicional no backend.

---

## Licença
- Uso interno / Não licenciado / Modificação não autorizada / Redistribuição não autorizada. 
- **Repressão a infrações autorais identificadas serão inflexíveis e severas.**


**© IFL & Co. Ltda.**, CNPJ nº [28.904.535;0001-06] -- Todos os direitos reservados.
Este material, incluindo código-fonte, arquitetura, lógica de funcionamento, layout, textos e quaisquer outros elementos, constitui obra protegida pela Lei nº 9.610/1998 e demais normas aplicáveis.
É permitido exclusivamente o uso da plataforma como ponto de venda, bem como a utilização dos resultados gerados por sua operação (incluindo links de redirecionamento associados às transações realizadas).
Fica expressamente proibida qualquer forma de acesso, cópia, reprodução, modificação, engenharia reversa, descompilação, distribuição, publicação, licenciamento, cessão, comercialização ou exploração, total ou parcial, ainda que com alterações, do código, da estrutura ou de quaisquer elementos da plataforma, sem autorização prévia e por escrito da IFL & Co. Ltda.
A utilização da plataforma não implica cessão ou transferência de quaisquer direitos de propriedade intelectual, permanecendo todos os direitos integralmente reservados à IFL & Co. Ltda.

A violação destas disposições sujeitará o infrator às sanções civis e penais cabíveis.
