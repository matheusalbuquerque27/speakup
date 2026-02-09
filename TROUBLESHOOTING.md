# 🚨 Solução de Problemas - GitHub Pages

## Problema: Exercícios não carregam no GitHub Pages

### ✅ Checklist Rápido

1. **Verifique se todos os arquivos foram commitados:**
   ```bash
   git status
   ```
   
   Certifique-se que `exercises.json` está no repositório:
   ```bash
   git add exercises.json
   git commit -m "Add exercises.json"
   git push
   ```

2. **Aguarde o deploy (1-2 minutos)**
   - Vá em: `Settings > Pages`
   - Verifique se o status está "✅ Your site is live"

3. **Limpe o cache do navegador:**
   - Chrome/Edge: `Ctrl + Shift + R` (Windows) ou `Cmd + Shift + R` (Mac)
   - Firefox: `Ctrl + F5`

4. **Use a ferramenta de verificação:**
   - Abra: `https://matheusalbuquerque27.github.io/speedup/verificar-sistema.html`
   - Veja quais arquivos estão carregando corretamente

---

## 🔧 Soluções Detalhadas

### Solução 1: Verificar Estrutura de Arquivos

Certifique-se que os arquivos estão na raiz ou na pasta correta:

```
speedup/
├── index.html          ✅
├── app.js              ✅
├── exercises.json      ✅ (IMPORTANTE!)
├── .nojekyll           ✅ (novo arquivo criado)
└── ...
```

**Comando para verificar:**
```bash
ls -la
```

---

### Solução 2: Verificar exercises.json

**Teste localmente primeiro:**

1. Abra o arquivo `exercises.json` no VSCode
2. Verifique se não há erros de sintaxe (o editor mostrará)
3. Teste localmente abrindo `index.html` no navegador

**Conteúdo deve ter:**
```json
{
  "monday": [ /* 20 exercícios */ ],
  "tuesday": [ /* 20 exercícios */ ],
  "wednesday": [ /* 20 exercícios */ ],
  "thursday": [ /* 20 exercícios */ ],
  "friday": [ /* 20 exercícios */ ]
}
```

---

### Solução 3: Verificar Configuração do GitHub Pages

1. Vá em: **Settings** > **Pages**
2. **Source:** Deve estar em "Deploy from a branch"
3. **Branch:** Selecione `main` (ou `master`)
4. **Folder:** Selecione `/ (root)` ou `/speedup` conforme estrutura

**Se os arquivos estão em uma subpasta:**
- Configure o branch para a pasta correta
- OU mova os arquivos para a raiz do repositório

---

### Solução 4: Adicionar .nojekyll

O arquivo `.nojekyll` já foi criado. Faça commit e push:

```bash
git add .nojekyll
git commit -m "Add .nojekyll for GitHub Pages"
git push
```

Isso garante que o GitHub Pages não processe os arquivos com Jekyll.

---

### Solução 5: Verificar CORS e Fetch

O código agora tenta 3 caminhos diferentes:

```javascript
const paths = [
    './exercises.json',
    'exercises.json',
    '/speedup/exercises.json'
];
```

Se nenhum funcionar, abra o **Console do Navegador** (F12) e veja o erro exato.

---

### Solução 6: Testar URLs Diretamente

Abra essas URLs no navegador para verificar se os arquivos estão acessíveis:

1. **exercises.json:**
   ```
   https://matheusalbuquerque27.github.io/speedup/exercises.json
   ```
   
2. **app.js:**
   ```
   https://matheusalbuquerque27.github.io/speedup/app.js
   ```

Se retornar **404**, o arquivo não está no repositório.

---

## 🔍 Diagnóstico com Console

Abra o **Console do Navegador** (F12) e veja as mensagens:

### ✅ Mensagem de Sucesso:
```
Exercícios carregados de: ./exercises.json
```

### ❌ Mensagem de Erro:
```
Erro ao carregar exercícios: Failed to fetch
```

**Se ver "Failed to fetch":**
- O arquivo não existe no servidor
- Problema de CORS (raro no GitHub Pages)
- Cache do navegador

---

## 📝 Comandos Git Úteis

### Ver status dos arquivos:
```bash
git status
```

### Adicionar todos os arquivos:
```bash
git add .
```

### Commit e push:
```bash
git commit -m "Fix exercises loading"
git push origin main
```

### Ver histórico:
```bash
git log --oneline
```

### Ver arquivos no último commit:
```bash
git ls-tree -r main --name-only
```

---

## 🌐 Verificar Deploy do GitHub Pages

1. Vá em: **Actions** (tab no topo do repositório)
2. Veja se o último workflow rodou com sucesso (✅)
3. Se falhou (❌), clique nele para ver o erro

---

## 🧪 Testar Localmente (100% certeza)

Antes de fazer commit, teste localmente:

### Opção 1: Python
```bash
cd speedup
python -m http.server 8000
```
Abra: `http://localhost:8000`

### Opção 2: Node.js (http-server)
```bash
npm install -g http-server
http-server
```

### Opção 3: VS Code (Live Server)
1. Instale a extensão "Live Server"
2. Clique direito em `index.html` > "Open with Live Server"

---

## 📊 Checklist Final

- [ ] `exercises.json` está no repositório
- [ ] Arquivo `exercises.json` é JSON válido
- [ ] Todos os arquivos foram commitados e pushed
- [ ] GitHub Pages está ativado (Settings > Pages)
- [ ] Branch correto selecionado (main/master)
- [ ] Aguardou 1-2 minutos após push
- [ ] Limpou o cache do navegador
- [ ] `.nojekyll` foi adicionado
- [ ] Testou a URL direta do exercises.json
- [ ] Verificou o Console (F12) por erros

---

## 🆘 Ainda não funciona?

### Verifique o arquivo `verificar-sistema.html`:

```
https://matheusalbuquerque27.github.io/speedup/verificar-sistema.html
```

Esta página fará diagnóstico completo e mostrará exatamente onde está o problema.

---

## 💡 Solução Rápida (Se nada funcionar)

Se nada funcionar, teste essa abordagem:

1. **Clone o repositório novamente:**
   ```bash
   git clone https://github.com/matheusalbuquerque27/speedup.git
   cd speedup
   ```

2. **Verifique se o arquivo existe:**
   ```bash
   ls -la exercises.json
   ```

3. **Se não existir, copie novamente:**
   - Copie o conteúdo de `exercises.json`
   - Crie o arquivo novamente
   - Faça commit e push

4. **Force o rebuild:**
   ```bash
   git commit --allow-empty -m "Rebuild GitHub Pages"
   git push
   ```

---

## 📞 Suporte

Se após todas essas etapas ainda não funcionar:

1. Abra o Console (F12)
2. Tire um screenshot do erro
3. Verifique se `exercises.json` está realmente no GitHub:
   ```
   https://github.com/matheusalbuquerque27/speedup/blob/main/exercises.json
   ```

---

**Última atualização:** 8 de fevereiro de 2026
