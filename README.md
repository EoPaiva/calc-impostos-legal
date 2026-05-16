# Legal — Calc Impostos BR uPaiva

Páginas legais da extensão (necessárias pra aprovar na Chrome Web Store).

## Arquivos

- **`privacidade.html`** — Política de Privacidade (LGPD + cobertura Web Store)
- **`termos.html`** — Termos de Uso (Premium, reembolso, disclaimer fiscal)

Ambos são HTML standalone com CSS embutido — sem dependência externa, sem JS, sem imagens
(logo é SVG inline). Funcionam em qualquer host estático.

## URLs configuradas na extensão

A extensão (`popup/popup.html`) aponta pra:

- `https://eopaiva.github.io/calc-impostos-legal/privacidade.html`
- `https://eopaiva.github.io/calc-impostos-legal/termos.html`

## Setup do GitHub Pages — passo a passo

### 1. Criar o repositório

1. Acessa <https://github.com/new>
2. Nome do repo: **`calc-impostos-legal`** (exatamente esse, pra bater com a URL)
3. Owner: **eopaiva**
4. **Public** (obrigatório pra GitHub Pages grátis)
5. NÃO marca "Add a README"
6. Clica **Create repository**

### 2. Subir os 2 arquivos

**Via web (mais simples, sem terminal):**
1. Na página vazia do repo, clica em **"uploading an existing file"**
2. Arrasta `privacidade.html` e `termos.html` da pasta `calculadora-impostos-freelancer/legal/`
3. Commit message: `Initial: Privacidade + Termos`
4. Clica **Commit changes**

**Via terminal (se preferir):**
```bash
cd C:/Users/mpaii/Documents/Claude/calculadora-impostos-freelancer/legal
git init
git add privacidade.html termos.html
git commit -m "Initial: Privacidade + Termos"
git branch -M main
git remote add origin https://github.com/eopaiva/calc-impostos-legal.git
git push -u origin main
```

### 3. Ativar GitHub Pages

1. No repo recém-criado: **Settings** → **Pages** (sidebar esquerda)
2. Source: **Deploy from a branch**
3. Branch: `main` / Folder: `/ (root)` → **Save**
4. Aguarda ~1 minuto. Depois aparece no topo da mesma página:
   > ✓ Your site is live at `https://eopaiva.github.io/calc-impostos-legal/`

### 4. Validar

Abre as 2 URLs no navegador (anônimo de preferência):
- <https://eopaiva.github.io/calc-impostos-legal/privacidade.html>
- <https://eopaiva.github.io/calc-impostos-legal/termos.html>

Ambas devem renderizar com a logo, navegação no topo, conteúdo formatado.

### 5. Confirmar links na extensão

Reload da extensão Calc Impostos → aba Config → seção "Sobre" → clica em **"Política de Privacidade"** e **"Termos de Uso"**. Cada um deve abrir a página certa em nova aba.

Também aparece embaixo do botão "Garantir acesso vitalício" no overlay Premium.

## Pra atualizar no futuro

Quando precisar mudar texto:

1. Edita o arquivo localmente em `calculadora-impostos-freelancer/legal/`
2. **Incrementa a versão** no topo do documento (ex.: "Versão 1.0" → "Versão 1.1")
3. Atualiza "Última atualização" pra data atual
4. Sobe pro GitHub:
   - **Via web:** abre o arquivo no GitHub → ícone do lápis → cola conteúdo novo → commit
   - **Via terminal:** `git add . && git commit -m "Update XYZ" && git push`
5. GitHub Pages atualiza automaticamente em ~1 minuto

### Quando vale incrementar versão e notificar usuários

**Política de Privacidade — atualiza se:**
- Mudar quais dados são coletados (ex.: passar a usar Google Analytics)
- Adicionar novo subprocessador (ex.: trocar Resend por SendGrid)
- Mudar regras de retenção de dados

**Termos — atualiza se:**
- Mudar preço do Premium (R$ 19,99 → outro valor)
- Mudar limite de dispositivos (atualmente 2)
- Mudar política de reembolso (atualmente 7 dias)
- Mudar o que entra no Free vs Premium

Pra mudanças relevantes, **notifique usuários Premium por e-mail com 30 dias de antecedência**
(cláusula 12 dos Termos).

## Alternativas se quiser sair do GitHub Pages

Se um dia migrar pra outro host (Hostinger, Cloudflare Pages, Vercel), só precisa:

1. Subir os arquivos no host novo
2. Atualizar 4 ocorrências em `popup/popup.html` substituindo `https://eopaiva.github.io/calc-impostos-legal/` pelo novo URL base

## Antes de submeter à Chrome Web Store

- [ ] GitHub Pages ativo e ambas URLs respondem com 200
- [ ] Email `suporte@upaiva.dev` está recebendo (testa mandando 1 email pra ele)
- [ ] Data de "Última atualização" está atualizada nos 2 documentos
- [ ] Reload da extensão e confirme que os links no Config + Premium overlay abrem as páginas certas
