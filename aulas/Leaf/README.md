# 🍃 Leaf Level - A2 Intermediate to Advanced

## Sobre o Nível Leaf

O nível **Leaf** é destinado a alunos que já possuem conhecimento intermediário de inglês (A2) e desejam avançar para um nível mais avançado de conversação e compreensão.

## Estrutura

### 📚 Lessons
Cada lição contém:
- Slides de apresentação (`.md` ou `.pdf`)
- Material didático do aluno (`.md` ou `.pdf`)
- Exercícios práticos de listening, speaking, reading e writing

### 🎙️ Podcasts
Podcasts temáticos para prática de listening com:
- Arquivo de áudio (`.wav`)
- Script completo (`.md`)
- Vocabulário-chave
- Exercícios de compreensão

## Tópicos Abordados

- Conversação avançada
- Tempos verbais complexos (conditional sentences, perfect tenses)
- Vocabulário profissional
- Expressões idiomáticas
- Debates e discussões
- Apresentações formais

## Como Adicionar Conteúdo

### Para adicionar vídeos:
Edite o arquivo `app.js` na seção de vídeos do Leaf:
```javascript
} else if (currentLevel === 'leaf') {
    videos = [
        { title: '📚 Leaf - Lesson 01', url: 'https://www.youtube.com/embed/VIDEO_ID' },
    ];
}
```

### Para adicionar podcasts:
1. Adicione o arquivo de áudio em `Leaf/Podcasts/podcast_episodeXX.wav`
2. Adicione o script em `Leaf/Podcasts/podcast_scriptXX.md`
3. Edite o array de podcasts em `app.js`

### Para adicionar exercícios:
Crie o arquivo `exercises-leaf.json` seguindo o formato dos outros níveis.

## Status Atual

- [ ] Lesson 01 - Em desenvolvimento
- [ ] Podcasts - A ser criado
- [ ] Vídeos - A ser criado
- [ ] Exercícios - A ser criado
