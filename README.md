🎨 AI Art Gallery - Galeria Virtual de Artes com IA

Uma galeria virtual moderna para exibir e gerenciar obras de arte criadas por inteligência artificial, construída com Supabase e Bootstrap.

✨ Funcionalidades

🖼️ Galeria de Obras

· Visualização de obras de arte geradas por IA
· Filtros por modelo de IA (Stable Diffusion, DALL-E, Midjourney)
· Informações detalhadas sobre cada obra
· Sistema de preços por visualização
· Modal para visualizar prompts utilizados

🔐 Sistema de Autenticação

· Cadastro e login de usuários
· Diferentes níveis de acesso (free, premium, collector)
· Perfil de usuário personalizado
· Gestão de sessões

⚡ Painel Administrativo

· Dashboard com estatísticas
· CRUD completo de obras de arte
· Controle de status (publicado/rascunho)
· Gerenciamento de usuários
· Métricas de visualizações e curtidas

💰 Sistema de Assinatura

· Planos básico, premium e colecionador
· Diferentes níveis de acesso ao conteúdo
· Preços flexíveis por visualização ou mensal

🛠️ Console de Desenvolvimento

· Interface para configuração do banco
· Teste de conexão em tempo real
· Criação de dados de exemplo
· Logs detalhados do sistema

🚀 Tecnologias Utilizadas

· Frontend: HTML5, CSS3, Bootstrap 5.3
· Backend: Supabase (PostgreSQL + Auth)
· Icons: Font Awesome 6.4
· Deploy: Hospedagem estática (Netlify, Vercel, etc.)

📦 Estrutura do Projeto

```
ai-art-gallery/
├── index.html                 # Página principal
├── README.md                  # Documentação
└── assets/                   # Recursos estáticos
    ├── css/
    ├── js/
    └── images/
```

🏁 Como Configurar

1. Clone o Repositório

```bash
git clone https://github.com/seu-usuario/ai-art-gallery.git
cd ai-art-gallery
```

2. Configuração do Supabase

1. Crie uma conta em Supabase
2. Crie um novo projeto
3. Substitua as credenciais no arquivo galeria.html:

```javascript
const SUPABASE_URL = 'sua-url-do-supabase';
const SUPABASE_ANON_KEY = 'sua-chave-anon';
```

3. Configuração do Banco de Dados

Execute o seguinte SQL no editor SQL do Supabase:

```sql
CREATE TABLE IF NOT EXISTS users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email VARCHAR(255) UNIQUE NOT NULL,
    full_name VARCHAR(255) NOT NULL,
    user_type VARCHAR(50) DEFAULT 'viewer',
    subscription_tier VARCHAR(50) DEFAULT 'free',
    created_at TIMESTAMPTZ DEFAULT NOW()
);

CREATE TABLE IF NOT EXISTS artworks (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    title VARCHAR(255) NOT NULL,
    description TEXT,
    artist_id UUID REFERENCES users(id),
    image_url TEXT NOT NULL,
    ai_model VARCHAR(100),
    ai_prompt TEXT,
    access_tier VARCHAR(50) DEFAULT 'free',
    price_per_view DECIMAL(5,2) DEFAULT 1.00,
    status VARCHAR(50) DEFAULT 'draft',
    view_count INTEGER DEFAULT 0,
    like_count INTEGER DEFAULT 0,
    created_at TIMESTAMPTZ DEFAULT NOW()
);
```

4. Execução Local

Abra o arquivo galeria.html em um servidor web local ou execute:

```bash
# Com Python
python -m http.server 8000

# Com Node.js
npx http-server
```

🎯 Como Usar

Para Visitantes

1. Acesse a galeria principal
2. Visualize obras em destaque
3. Clique em "Ver Prompt" para ver os detalhes da criação
4. Crie uma conta para acessar mais recursos

Para Artistas

1. Faça login na plataforma
2. Acesse o painel administrativo
3. Adicione novas obras
4. Gerencie suas criações

Para Administradores

1. Acesse o painel administrativo
2. Visualize estatísticas do sistema
3. Gerencie todas as obras e usuários
4. Monitore métricas de engajamento

🔧 Funcionalidades Técnicas

Console de Desenvolvimento

· Teste de conexão com Supabase
· Criação automática de tabelas
· Geração de dados de exemplo
· Logs em tempo real do sistema

Sistema de Autenticação

· Cadastro seguro de usuários
· Validação de e-mail
· Gestão de sessões
· Recuperação de senha

API Integrada

· Operações CRUD completas
· Queries otimizadas com Supabase
· Filtros e ordenação
· Contagem de métricas

🎨 Personalização

Cores do Tema

Modifique as variáveis CSS no :root:

```css
:root {
    --primary-color: #6c63ff;
    --secondary-color: #4a44b5;
    --dark-color: #1a1a2e;
    --light-color: #f8f9fa;
}
```

Modelos de IA Suportados

· Stable Diffusion
· DALL-E
· Midjourney
· Outros modelos personalizados

📱 Responsividade

O projeto é totalmente responsivo e funciona em:

· 📱 Dispositivos móveis
· 💻 Tablets
· 🖥️ Desktops

🤝 Contribuição

1. Faça o fork do projeto
2. Crie uma branch para sua feature (git checkout -b feature/AmazingFeature)
3. Commit suas mudanças (git commit -m 'Add some AmazingFeature')
4. Push para a branch (git push origin feature/AmazingFeature)
5. Abra um Pull Request

📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

🛠️ Desenvolvimento Futuro

· Sistema de pagamentos integrado
· Upload de imagens direto na plataforma
· Geração de obras com IA integrada
· Sistema de comentários e avaliações
· API REST para integrações
· App mobile nativo

📞 Suporte

Em caso de dúvidas ou problemas:

1. Verifique a documentação do Supabase
2. Consulte os logs do console de desenvolvimento
3. Abra uma issue no GitHub

---

Desenvolvido com ❤️ usando Supabase e Bootstrap
