# JsonRegister - Vue.js 3

A modern and complete online JSON formatter, developed with Vue.js 3, CodeMirror 6 and Tailwind CSS. Offers formatting, validation, advanced search, JSON paths extraction and many other features for developers.

![JsonRegister](https://img.shields.io/badge/Vue.js-3.4-4FC08D?style=flat-square&logo=vue.js)
![CodeMirror](https://img.shields.io/badge/CodeMirror-6.0-orange?style=flat-square)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.3-38B2AC?style=flat-square&logo=tailwind-css)

## ✨ Funcionalidades

### 🎯 Funcionalidades Principais
- **Formatação Automática**: Parse e formatação de JSON em tempo real com debounce de 300ms
- **Syntax Highlighting**: CodeMirror 6 com destaque de sintaxe para JSON
- **Validação Inteligente**: Detecção de erros com mensagens detalhadas e localização aproximada
- **Interface Responsiva**: Layout adaptável para desktop, tablet e mobile

### 🛠️ Ferramentas para Desenvolvedores
- **Beautify**: Formata JSON com indentação de 2 espaços
- **Minify**: Compacta JSON removendo espaços desnecessários
- **Copiar**: Copia JSON formatado para área de transferência
- **Exportar**: Download do JSON como arquivo .json
- **Limpar**: Limpa todos os campos

### 🔍 Busca Avançada
- **Busca em Tempo Real**: Encontra chaves e valores no JSON
- **Suporte a Regex**: Busca avançada com expressões regulares
- **Resultados Detalhados**: Mostra caminho completo e tipo de resultado
- **Limitação de Performance**: Máximo de 50 resultados para otimização

### 📚 Histórico Local
- **Armazenamento Automático**: Salva últimos 5 JSONs processados
- **Restauração Rápida**: Clique para restaurar JSONs anteriores
- **Informações Detalhadas**: Timestamp, tamanho e preview
- **Gerenciamento**: Remover itens individuais ou limpar tudo

### 🎨 Temas e Personalização
- **Modo Claro/Escuro**: Toggle automático com preferência do sistema
- **CSS Variables**: Temas consistentes em toda aplicação
- **Transições Suaves**: Animações elegantes entre estados
- **Acessibilidade**: Suporte completo a navegação por teclado

## 🚀 Instalação e Execução

### Pré-requisitos
- Node.js 16+ 
- npm ou yarn

### Passos para Instalação

1. **Clone ou baixe o projeto**
   ```bash
   # Se usando Git
   git clone <url-do-repositorio>
   cd json-formatter-vue
   
   # Ou extraia os arquivos do projeto na pasta desejada
   ```

2. **Instale as dependências**
   ```bash
   npm install
   # ou
   yarn install
   ```

3. **Execute o servidor de desenvolvimento**
   ```bash
   npm run dev
   # ou
   yarn dev
   ```

4. **Acesse a aplicação**
   ```
   http://localhost:3000
   ```

### Comandos Disponíveis

```bash
# Desenvolvimento
npm run dev          # Inicia servidor de desenvolvimento

# Produção  
npm run build        # Gera build de produção
npm run preview      # Preview do build de produção
```

## 🎯 Como Usar

### Interface Principal

1. **Área de Entrada (Esquerda)**
   - Cole ou digite JSON na textarea
   - Validação automática em tempo real
   - Indicadores visuais de status (válido/inválido)
   - Contador de caracteres e tamanho do arquivo

2. **Área de Saída (Direita)**
   - JSON formatado com syntax highlighting
   - Controles para numeração de linhas e quebra de texto
   - Informações do JSON (tipo, tamanho, profundidade)

3. **Painel de Ações (Superior)**
   - Botões para formatação e manipulação
   - Campo de busca com resultados em tempo real
   - Modal de exportação com nome personalizado

4. **Histórico (Lateral)**
   - Lista dos últimos JSONs processados
   - Clique para restaurar qualquer item
   - Gerenciamento individual de itens

### Atalhos de Teclado

- `Ctrl/Cmd + B`: Formatar JSON (Beautify)
- `Ctrl/Cmd + M`: Minificar JSON
- `Ctrl/Cmd + L`: Limpar campos
- `Ctrl/Cmd + E`: Exportar arquivo
- `Ctrl/Cmd + H`: Alternar histórico
- `Ctrl/Cmd + D`: Alternar tema

### Busca Avançada

```javascript
// Exemplos de busca:
"nome"              // Busca literal
"email.*@gmail"     // Regex para emails do Gmail
"id"                // Encontra chaves ou valores com "id"
"^user"             // Chaves que começam com "user"
"\\d{4}"            // Números de 4 dígitos
```

## 🏗️ Arquitetura do Projeto

### Estrutura de Pastas
```
src/
├── components/          # Componentes Vue
│   ├── JsonEditor.vue   # Editor de entrada
│   ├── JsonOutput.vue   # Saída com CodeMirror
│   ├── ActionButtons.vue # Botões de ação
│   └── HistoryPanel.vue # Painel de histórico
├── composables/         # Composition API
│   ├── useJsonParser.js # Lógica de parsing
│   ├── useTheme.js      # Gerenciamento de tema
│   ├── useHistory.js    # Histórico local
│   ├── useClipboard.js  # Área de transferência
│   └── useJsonSearch.js # Busca no JSON
├── utils/              # Utilitários
│   └── fileExport.js   # Exportação de arquivos
├── App.vue            # Componente principal
├── main.js           # Ponto de entrada
└── style.css         # Estilos globais
```

### Tecnologias Utilizadas

- **Vue.js 3**: Framework reativo com Composition API
- **Vite**: Build tool moderna e rápida
- **CodeMirror 6**: Editor de código com syntax highlighting
- **Tailwind CSS**: Framework CSS utilitário
- **Vue Toastification**: Notificações elegantes
- **Lodash**: Utilitários JavaScript (debounce, get)

### Composables (Composition API)

#### `useJsonParser`
- Parsing e validação de JSON
- Formatação (beautify/minify)
- Sanitização contra XSS
- Debounce para performance

#### `useTheme`
- Gerenciamento de tema claro/escuro
- Persistência no localStorage
- Detecção de preferência do sistema
- Aplicação de CSS variables

#### `useHistory`
- Armazenamento local dos últimos 5 JSONs
- Serialização/deserialização segura
- Geração de previews
- Formatação de timestamps e tamanhos

#### `useClipboard`
- API moderna de clipboard
- Fallback para navegadores antigos
- Feedback visual com toasts
- Tratamento de erros

#### `useJsonSearch`
- Busca recursiva em objetos/arrays
- Suporte a expressões regulares
- Limitação de resultados para performance
- Destaque de texto encontrado

## 🔧 Configuração Avançada

### Personalização de Temas

Edite as CSS variables em `src/style.css`:

```css
:root {
  --bg-primary: #ffffff;
  --bg-secondary: #f8fafc;
  --text-primary: #1e293b;
  --accent-color: #3b82f6;
  /* ... outras variáveis */
}
```

### Configuração do CodeMirror

Modifique `src/components/JsonOutput.vue` para personalizar:

```javascript
const extensions = [
  basicSetup,
  json(),
  EditorView.theme({
    '&': { fontSize: '14px' }, // Tamanho da fonte
    '.cm-content': { padding: '16px' } // Padding interno
  })
]
```

### Ajustes de Performance

- **Debounce**: Altere o delay em `useJsonParser.js` (padrão: 300ms)
- **Histórico**: Modifique `maxHistorySize` em `useHistory.js` (padrão: 5 itens)
- **Busca**: Ajuste limite de resultados em `useJsonSearch.js` (padrão: 50)

## 🔒 Segurança

- **Sanitização XSS**: Remove scripts maliciosos do JSON
- **Validação de Entrada**: Parse seguro com try/catch
- **CSP Ready**: Compatível com Content Security Policy
- **Sem Execução de Código**: JSON é apenas parseado, nunca executado

## 🌐 Compatibilidade

### Navegadores Suportados
- Chrome 88+
- Firefox 85+
- Safari 14+
- Edge 88+

### Funcionalidades Progressivas
- **Clipboard API**: Fallback para `document.execCommand`
- **CSS Grid**: Fallback para Flexbox
- **Backdrop Filter**: Fallback para cores sólidas

## 📝 Licença

Este projeto é open source e está disponível sob a licença MIT.

## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer fork do projeto
2. Criar uma branch para sua feature
3. Commit suas mudanças
4. Fazer push para a branch
5. Abrir um Pull Request

## 📞 Suporte

Se encontrar algum problema ou tiver sugestões:

1. Verifique se o Node.js está atualizado (16+)
2. Limpe o cache: `npm clean-install`
3. Verifique o console do navegador para erros
4. Teste em modo incógnito para descartar extensões

## 🎉 Créditos

Desenvolvido com ❤️ usando as melhores práticas de desenvolvimento moderno:

- **Vue.js Team** - Framework reativo incrível
- **CodeMirror** - Editor de código poderoso
- **Tailwind Labs** - CSS framework utilitário
- **Vite Team** - Build tool ultrarrápida
