# 🌟 SpeakUp - Exercícios de Fixação

Sistema de exercícios de repetição espaçada para aprendizagem de inglês, baseado nos métodos **Kumon** e **Duolingo**.

## 📁 Estrutura do Projeto

```
speedup/
├── index.html              # Interface principal do sistema
├── app.js                  # Lógica de negócio
├── exercises.json          # Base de exercícios (5 dias x 20 exercícios)
├── visualizar-dados.html   # Visualizador de resultados salvos
├── test-api.html           # Testador de envio para API
├── api_example.js          # Exemplos de API para integração
├── API-FORMAT.md           # Documentação do formato de dados da API
├── README_EXERCISES.md     # Documentação detalhada do sistema
├── GUIA-RAPIDO.md          # Tutorial de início rápido
├── agents.md               # Definição dos agentes do projeto
├── aulas/                  # Conteúdo das lições
│   ├── Seed/               # Nível iniciante
│   │   └── Lesson01/       # Greetings & Introductions
│   └── Root/               # Nível intermediário
└── arquivos/               # Documentos e PDFs
```

## 🎯 Funcionalidades

### ✅ Sistema de Exercícios
- **Menu semanal**: Segunda a Sexta-feira
- **20 exercícios por dia** com repetição espaçada
- **5 tipos de exercícios**: Fill-blank, Multiple Choice, Translate, Complete, Match
- **Barra de progresso** em tempo real
- **Sistema de pontuação** automático
- **Interface responsiva** e moderna

### 📊 Visualizador de Dados
- Dashboard com estatísticas gerais
- Visualização detalhada de cada envio
- Indicadores visuais de acertos/erros
- Exportação de dados em JSON
- Gerenciamento de histórico

### 🔗 Integração com API
- Envio automático via POST
- Backup local no localStorage
- Exemplos de implementação (Node.js, Python, Firebase)
- Suporte para webhooks (Zapier, Make, n8n)

## 🚀 Como Usar

### 1. Configuração Inicial

**Configure a URL da API** no arquivo `app.js`:

```javascript
const API_URL = 'https://sua-api.com/exercises'; // Altere aqui
```

### 2. Executar o Sistema

Abra o arquivo `index.html` em um navegador web moderno.

### 3. Realizar Exercícios

1. Escolha o dia da semana
2. Responda os 20 exercícios
3. Clique em "Enviar Respostas"

### 4. Visualizar Resultados

Abra o arquivo `visualizar-dados.html` para ver:
- Estatísticas gerais
- Histórico de envios
- Detalhes de cada exercício
- Exportação de dados

## 📚 Metodologia - Repetição Espaçada

O sistema segue o método de repetição espaçada para maximizar a retenção:

| Dia | Foco |
|-----|------|
| **Segunda** | Vocabulário básico e primeiros conceitos |
| **Terça** | Reforço dos conceitos + novos exemplos |
| **Quarta** | Consolidação e variações |
| **Quinta** | Integração dos conceitos |
| **Sexta** | Revisão geral da semana |

## 🎓 Conteúdo Atual

### Seed - Lesson 01: Greetings & Introductions

**Vocabulário:**
- Greetings (Hello, Hi, Goodbye, Good morning, etc.)
- Personal pronouns (I, You, He, She, It, We, They)
- Verb "To Be" (am, is, are)
- Basic expressions (What's your name?, How are you?, Nice to meet you)

**100 exercícios totais** (20 por dia, 5 dias)

## 🛠️ Tecnologias

- **HTML5**: Estrutura semântica
- **CSS3**: Design responsivo com gradientes e animações
- **JavaScript (Vanilla)**: Lógica de negócio sem dependências
- **JSON**: Armazenamento de exercícios
- **Fetch API**: Comunicação com servidor
- **LocalStorage API**: Backup local automático

## 📋 Requisitos

- Navegador moderno (Chrome 90+, Firefox 88+, Edge 90+)
- JavaScript habilitado
- Conexão com internet (para envio à API)

## 📖 Documentação Adicional

- **[API-FORMAT.md](API-FORMAT.md)** - Documentação completa do formato de dados da API
- **[README_EXERCISES.md](README_EXERCISES.md)** - Documentação completa do sistema de exercícios
- **[GUIA-RAPIDO.md](GUIA-RAPIDO.md)** - Tutorial de início rápido
- **[api_example.js](api_example.js)** - Exemplos de implementação de API
- **[test-api.html](test-api.html)** - Ferramenta para testar envio de dados
- **[agents.md](agents.md)** - Definição dos agentes do projeto SpeakUp

## 🔧 Personalização

### Adicionar Novos Exercícios

Edite o arquivo `exercises.json` seguindo o padrão:

```json
{
  "type": "fill-blank|multiple-choice|translate|complete|match",
  "question": "Sua pergunta aqui",
  "correctAnswer": "resposta|resposta alternativa",
  "options": ["A", "B", "C"] // Apenas para multiple-choice
}
```

### Alterar Cores

Edite as variáveis CSS no `index.html`:

```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

## 📊 Estrutura dos Dados Enviados para API

O sistema envia os dados no seguinte formato:

```json
{
  "timestamp": "2026-02-08T14:30:00.000Z",
  "student": "Nome do Aluno",
  "worksheetId": "monday_lesson01_seed",
  "total": 20,
  "correct": 18,
  "payload": [
    {
      "exerciseNumber": 1,
      "type": "multiple-choice",
      "question": "Como se diz 'Olá' em inglês?",
      "correctAnswer": "Hello",
      "userAnswer": "Hello",
      "isCorrect": true
    }
    // ... mais 19 exercícios
  ]
}
```

### Campos Principais

- **`timestamp`**: Data/hora do envio (ISO 8601)
- **`student`**: Nome do estudante
- **`worksheetId`**: ID da planilha (formato: `{dia}_lesson01_seed`)
  - Exemplos: `monday_lesson01_seed`, `tuesday_lesson01_seed`, etc.
- **`total`**: Total de exercícios (sempre 20)
- **`correct`**: Número de acertos
- **`payload`**: Array com todos os exercícios e respostas

📄 **Documentação completa:** Ver [API-FORMAT.md](API-FORMAT.md)

## 🐛 Solução de Problemas

### Exercícios não carregam
- Verifique se `exercises.json` está na mesma pasta
- Abra o console do navegador (F12) para ver erros

### Erro ao enviar
- Verifique a URL da API em `app.js`
- Verifique sua conexão com a internet
- Os dados são salvos localmente mesmo se falhar

### Dados não aparecem no visualizador
- Faça ao menos um exercício e envie
- Verifique o localStorage do navegador

## 🎨 Screenshots

### Menu Principal
Interface com botões para cada dia da semana.

### Página de Exercícios
20 exercícios com barra de progresso e tipos variados.

### Visualizador de Dados
Dashboard com estatísticas e detalhes de cada envio.

## 📞 Suporte

Para dúvidas sobre o sistema de exercícios ou integração com API, consulte a documentação detalhada em `README_EXERCISES.md` ou o arquivo de exemplos `api_example.js`.

## 📝 Licença

Este sistema foi desenvolvido exclusivamente para uso nas turmas SpeakUp.

---

**Desenvolvido para SpeakUp** 🌟
**Método de Repetição Espaçada** | **Baseado em Kumon & Duolingo**
