# Projeto Laravel com Livewire, TailwindCSS e AlpineJS

Projeto de estudo de novas tecnologias e práticas de desenvolvimento.

## Tecnologias Utilizadas

- **PHP 8.3**
- **Laravel 11**
- **Livewire 3**
- **TailwindCSS 3**
- **AlpineJS**
- **Laravel Herd**
- **Mailpit** (para notificação por email)
- **Filas de Notificações** (Queue)
- **Tarefas Agendadas** (Cron)
- **Docker** (para Mailpit)
- **Sqlite**

## Instalação

Siga os passos abaixo para configurar o ambiente de desenvolvimento.

### 1. Instalar Dependências

Use o Composer e o NPM para instalar as dependências do backend e frontend:

```bash
composer install
npm install
```

### 2. Configuração do Banco de Dados

Criar as tabelas no banco de dados:
```bash
php artisan migrate
```

Dropar e Criar todas as tabelas no banco de dados:
```bash
php artisan migrate:fresh
```

Inserir Registros no Banco de Dados
```bash
php artisan db:seed
```

### 3. Configuração do Mailpit
Mailpit é utilizado para capturar e visualizar emails enviados pela aplicação no ambiente de desenvolvimento.

Iniciar o Mailpit
```bash
docker-compose up -d
```

Adicione ou atualize as seguintes variáveis no arquivo .env para conectar ao Mailpit:
```env
MAIL_MAILER=smtp
MAIL_HOST=127.0.0.1
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="no-replay@example.com"
MAIL_FROM_NAME="${APP_NAME}"
```

### 4. Executar o Worker de Filas
Rodar o serviço de fila para processar as notificações em background:
```bash
php artisan queue:work
```

### 5. Agendar Tarefas (Cron)
Para processar as tarefas agendadas, como fechar projetos que passaram da data limite, rode o seguinte comando:
```bash
php artisan schedule:work
```

### 6. Inicializar a Aplicação
Inicie o servidor backend para acessar a aplicação:
```bash
php artisan serve
```

Inicie o servidor frontend para compilar o TailwindCSS:
```bash
npm run dev
```

##

Referência: Projeto baseado no Curso Online de PHP com Rafael Lunardelli na [Rocketseat](https://app.rocketseat.com.br/).


