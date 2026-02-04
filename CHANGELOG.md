# Changelog

Todas as mudanças notáveis neste projeto serão documentadas neste arquivo.

## [1.1.0] - 2026-02-04

### ✨ Adicionado
- **Salvamento automático de progresso**: Continue de onde parou se fechar o navegador
- **Banner "Bem-vindo de volta"**: Mostra em qual pergunta o usuário parou
- **Tela de loading profissional**: 2.5s com textos dinâmicos
- **Resumo do perfil**: Mostra situação, experiência, objetivo e meta no resultado
- **Recomendação secundária**: Sugere 2º produto com % de compatibilidade
- **Timeline de implementação**: Jornada de 90 dias visual para cada produto
- **Cupom personalizado**: Código único gerado com base no email
- **Personalização visual por produto**: Cores dinâmicas do gradiente de fundo
- **Google Analytics**: Tracking de eventos (started, continued, completed, CTA clicked)
- **Progresso numérico**: "Pergunta X de 15" mais visível

### 🔄 Modificado
- **Pergunta 2 corrigida**: Removido parêntese confuso "(ou pretende atuar)"
  - Antes: "Há quanto tempo você atua (ou pretende atuar) na área?"
  - Depois: "Qual é a sua experiência na área de engenharia?"
- **Copy melhorado** na tela inicial: Mais direto e profissional
- **Estimativa de tempo**: Adicionado "⏱️ Tempo estimado: 3 minutos"
- **Subtítulos dos produtos**: Mais objetivos e focados em resultados
- **Botão CTA**: Texto mais impactante ("GARANTIR MINHA VAGA")

### 🎨 Melhorias de UX
- Toda a área da opção é clicável (não só o checkbox)
- `user-select: none` para evitar seleção de texto ao clicar
- `flex-shrink: 0` no input para não encolher
- Animações mais suaves
- Feedback visual melhorado ao selecionar opções

### 📝 Copy & Conteúdo
- Tom mais profissional (alinhado com branding do Vinicius)
- Foco em resultados práticos e números
- Timeline realista de 90 dias
- Benefícios reescritos de forma mais clara

## [1.0.0] - 2026-02-04

### ✨ Lançamento Inicial
- Quiz com 15 perguntas estratégicas
- Sistema de pontuação para 4 produtos
- Design responsivo e profissional
- Validação de formulário
- Navegação entre perguntas (voltar/próxima)
- Barra de progresso visual
- Tela de resultado personalizada

### 🔒 Segurança (OWASP Top 10)
- **A03:2021 - Proteção XSS**:
  - Função `sanitizeInput()` que escapa caracteres perigosos
  - Uso de `textContent` em vez de `innerHTML`
  - Função `createSafeElement()` para criação segura
- **A05:2021 - Security Configuration**:
  - Meta tags CSP (Content Security Policy)
  - `X-Content-Type-Options: nosniff`
  - `X-Frame-Options: DENY`
  - `X-XSS-Protection: 1; mode=block`
- **Validações**:
  - Nome: apenas letras e espaços (regex)
  - Email: formato correto (regex)
  - Telefone: formato brasileiro (regex)
  - Limite de tamanho (`maxlength`) em todos os campos
- **Proteção contra Tabnabbing**:
  - `rel="noopener noreferrer"` em links externos

### 📦 Produtos Incluídos
- PPCI do Zero ao Aprovado (R$ 599,90)
- Guia AVCB, CLCB e Laudos (R$ 349,90)
- Construindo um Escritório Lucrativo (R$ 499,90)
- Mentoria Individual (R$ 1.000-1.800)

### 🛠️ Tecnologias
- HTML5 + CSS3 + JavaScript Vanilla
- Single-file application (fácil deploy)
- Sem dependências externas
- Mobile-first design

---

## Formato de Versionamento

Este projeto segue [Semantic Versioning](https://semver.org/):
- **MAJOR**: Mudanças incompatíveis na API
- **MINOR**: Funcionalidades adicionadas (compatível)
- **PATCH**: Correções de bugs (compatível)

### Tipos de Mudanças
- **Adicionado**: Novas features
- **Modificado**: Mudanças em features existentes
- **Removido**: Features removidas
- **Corrigido**: Correções de bugs
- **Segurança**: Vulnerabilidades corrigidas
- **Depreciado**: Features que serão removidas
