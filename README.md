# Quiz de Produtos — Vinicius Figueiredo

Quiz interativo que ajuda o visitante em dúvida a descobrir **qual dos 4 produtos de engenharia** é ideal para o seu momento profissional, com um algoritmo de recomendação preciso e à prova de viés.

> **Arquivo principal:** `index.html` (single-file, sem build, sem dependências).
> Basta abrir no navegador ou hospedar estático.

## 🎯 Objetivo

Os 4 produtos têm fronteiras que se sobrepõem. O quiz precisa direcionar **corretamente** cada pessoa para o produto certo, sem favorecer nenhum por acaso. A recomendação é baseada em:

- **Intenção** — o que a pessoa fundamentalmente quer (serviços, dores, o que precisa agora)
- **Perfil** — quem ela é e seu contexto (momento de carreira, nível técnico, tempo, orçamento)

## 📦 Produtos

| Produto | Preço | Checkout |
|---|---|---|
| PPCI do Zero ao Aprovado | R$ 649,90 | Eduzz |
| Guia AVCB, CLCB e Laudos | R$ 449,90 | Eduzz |
| Escritório de Projetos Lucrativo | R$ 549,90 | Eduzz |
| Mentoria Individual com Vinicius | a partir de R$ 1.200 | Formulário |

> Conteúdos, benefícios, links e preços alinhados às páginas oficiais dos cursos (base Notion do Vinicius).

## 🧠 Algoritmo de recomendação

Documento completo e didático em **[`docs/Sistema-de-Pontuacao-Quiz-VF.pdf`](docs/Sistema-de-Pontuacao-Quiz-VF.pdf)**.

Resumo:

1. **Coleta** — 13 perguntas (escolha única e múltipla com limite).
2. **Soma** — cada opção marcada distribui pontos entre os 4 produtos.
3. **Ranking** — ordena por pontuação total; desempata por **intenção** e, em último caso, por prioridade fixa (`mentoria > ppci > avcb > escritorio`).
4. **Confiança** — a folga do 1º sobre o 2º vira a **% de compatibilidade** (`72% + folga × 26%`, limitada a 72–98%).
5. **Cross-sell** — o 2º colocado aparece como "próximo passo", com uma % menor e discreta.

### Rebalanceamento (v2.0)

Sob respostas aleatórias, a versão anterior favorecia AVCB/Escritório. Os **pesos** foram reotimizados (sem alterar perguntas/textos) para equilibrar:

| Produto | Antes | Depois |
|---|---|---|
| PPCI | 14% | **27%** |
| AVCB | 38% | **27%** |
| Escritório | 35% | **27%** |
| Mentoria | 12% | **19%** |

- Validado em **+150 mil simulações** e com **7 perfis-modelo** (7/7 corretos, 82–93% de compatibilidade).
- Método: otimização (hill-climbing) sobre os pesos, com as 7 personas como restrição rígida.

## 🚀 Features

- ✅ 13 perguntas estratégicas com validação
- ✅ Algoritmo intenção × perfil rebalanceado e à prova de viés
- ✅ % de compatibilidade (principal) + produto complementar (2º colocado)
- ✅ Resumo personalizado do perfil + timeline de 90 dias
- ✅ Salvamento automático de progresso (retomar de onde parou)
- ✅ Tema dark de autoridade técnica, **mobile-first** e 100% responsivo
- ✅ Ícones oficiais das redes sociais
- ✅ Acessibilidade (ARIA, foco visível, `prefers-reduced-motion`)
- ✅ Segurança baseada em OWASP

## 🔒 Segurança

- **XSS (A03)** — sanitização de inputs, uso de `textContent`, validação de nome/email/telefone por regex.
- **Misconfiguration (A05)** — CSP (`default-src 'self'`, `base-uri`, `form-action`), `X-Content-Type-Options: nosniff`, `Referrer-Policy`.
- **Tabnabbing** — `rel="noopener noreferrer"` em todos os links externos.

> **Proteção contra clickjacking** (`frame-ancestors` / `X-Frame-Options`) só funciona como **header HTTP** — não via `<meta>`. Se desejado, configurar no host (ex.: `X-Frame-Options: DENY`).

## ⚙️ Pendências de configuração (lado do cliente)

Estas **não travam o uso** do quiz, mas devem ser feitas pela equipe que cuida do site/marketing do Vinicius:

- **Google Analytics (GA4)** — substituir o placeholder `G-XXXXXXXXXX` no `<head>` pelo ID real (`analytics.google.com → Admin → Fluxos de dados`). Enquanto for placeholder, nenhuma visita/clique é medido.
- **Captura de leads** — hoje nome/e-mail/WhatsApp ficam **apenas no navegador** (o formulário é estático aqui). A integração com planilha (Google Sheets) ou CRM/webhook precisa ser implementada futuramente pela equipe de site/marketing.

## 🛠️ Tecnologias

HTML5 · CSS3 (variáveis, container queries, `clamp()`) · JavaScript Vanilla (ES6+) · Google Analytics 4 · LocalStorage API. Sem framework, sem build.

## 📊 Analytics (eventos)

`quiz_started` · `quiz_continued` · `quiz_question_answered` · `quiz_completed` · `product_cta_clicked`

## 🚀 Deploy

**GitHub Pages:** Settings → Pages → branch `main` → salvar.
**Netlify:** arraste o `index.html` em [app.netlify.com/drop](https://app.netlify.com/drop).

## 🔄 Versionamento

- **v1.0** — versão original com segurança OWASP
- **v1.1** — MVP com melhorias de UX (15 perguntas)
- **v2.0** — algoritmo rebalanceado e validado, quiz enxugado para 13 perguntas, tema dark/mobile-first, % de compatibilidade + complementar, revisão técnica de conteúdo, ícones oficiais, limpeza de segurança

## 📝 Roadmap

**Fase 2 (equipe do cliente):** integração com Google Sheets/CRM · e-mail automático com resultado · webhook de leads.
**Fase 3:** dashboard de analytics · A/B testing de perguntas.

## 👨‍💻 Desenvolvimento

```bash
git clone [URL-DO-REPO]
# abra o index.html no navegador
```

## 📄 Licença

Desenvolvido por **João Carlos Chaves** para **Vinicius Figueiredo**.

---

**Versão:** 2.0
