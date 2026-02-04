# Quiz de Produtos - Vinicius Figueiredo

Quiz interativo para ajudar potenciais clientes a descobrir qual produto de engenharia é ideal para seu momento profissional.

## 🎯 Objetivo

Reduzir a indecisão de compra através de um questionário estratégico que recomenda o produto mais adequado baseado em:
- Perfil profissional
- Conhecimento técnico
- Objetivos de curto prazo
- Disponibilidade e recursos

## 🚀 Features

### v1.1 (Atual)
- ✅ 15 perguntas estratégicas com validação
- ✅ Sistema de pontuação inteligente
- ✅ Salvamento automático de progresso
- ✅ Tela de loading profissional
- ✅ Resumo personalizado do perfil
- ✅ Recomendação secundária (2º produto)
- ✅ Timeline de implementação (90 dias)
- ✅ Cupom exclusivo por usuário
- ✅ Personalização visual por produto
- ✅ Google Analytics integrado
- ✅ Segurança OWASP Top 10 aplicada

## 🔒 Segurança

Implementações baseadas no OWASP Top 10:
- **A03:2021 - Injection (XSS)**: Sanitização de inputs, uso de `textContent`, validação rigorosa
- **A05:2021 - Security Misconfiguration**: CSP, X-Content-Type-Options, X-Frame-Options, X-XSS-Protection
- **Validações**: Nome, email, telefone com regex
- **Proteção contra Tabnabbing**: `rel="noopener noreferrer"` em links externos

## 📦 Produtos

1. **PPCI do Zero ao Aprovado** (R$ 599,90)
2. **Guia AVCB, CLCB e Laudos** (R$ 349,90)
3. **Construindo um Escritório Lucrativo** (R$ 499,90)
4. **Mentoria Individual** (R$ 1.000-1.800)

## 🛠️ Tecnologias

- HTML5
- CSS3 (com variáveis CSS)
- JavaScript Vanilla (ES6+)
- Google Analytics 4
- LocalStorage API

## 📊 Analytics

Eventos trackados:
- `quiz_started`: Usuário iniciou o quiz
- `quiz_continued`: Retomou progresso salvo
- `quiz_question_answered`: Respondeu uma pergunta
- `quiz_completed`: Finalizou o quiz
- `product_cta_clicked`: Clicou no CTA de compra

## 🚀 Deploy

### Netlify (Recomendado)
1. Acesse [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arraste o arquivo `index.html`
3. Pronto!

### GitHub Pages
1. Faça push para o repositório
2. Vá em Settings → Pages
3. Selecione a branch `main`
4. Salve

## 🔄 Versionamento

- **v1.0** - Versão original com segurança OWASP
- **v1.1** - MVP com melhorias de UX e features profissionais

## 📝 Roadmap

### Fase 2 (Próxima)
- [ ] Integração com Google Sheets
- [ ] Email automático com resultado
- [ ] Webhook para CRM

### Fase 3
- [ ] WhatsApp automático
- [ ] Dashboard de analytics
- [ ] A/B Testing de perguntas

## 👨‍💻 Desenvolvimento

```bash
# Clonar repositório
git clone [URL-DO-REPO]

# Abrir no navegador
# Basta abrir o index.html
```

## 📄 Licença

Desenvolvido por João Carlos Chaves para Vinicius Figueiredo

---

**Versão:** 1.1  
**Data:** Fevereiro 2026
