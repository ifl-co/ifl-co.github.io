```
# IFL Redirect

Mecanismo simples de redirecionamento com base em parâmetros codificados na URL. Recebe dados via query string, interpreta no navegador e executa ações (ex.: envio para WhatsApp) conforme regras definidas.

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

Uso interno. Modificação permitida. Redistribuição não autorizada.
```
