# Taxi Service User Form and Validation

## Descrição

O **Taxi Service User Form and Validation** é uma aplicação web desenvolvida com **Django** para praticar formulários de usuário, validações personalizadas e relacionamentos entre motoristas e carros.

O sistema simula uma plataforma de gerenciamento de serviço de táxi, permitindo administrar motoristas, carros e fabricantes. Esta versão tem como foco a criação de motoristas, validação do número da licença e associação ou remoção do usuário logado em um carro.

## Funcionalidades

- Listagem de motoristas, carros e fabricantes;
- Visualização de detalhes de carros e motoristas;
- Criação e exclusão de motoristas;
- Atualização do número da licença do motorista;
- Validação personalizada do formato da licença;
- Associação do usuário logado a um carro;
- Remoção do usuário logado de um carro;
- Uso de checkboxes para atribuir motoristas a carros;
- Proteção de páginas com autenticação;
- Uso de formulários e Class-Based Views.

## Tecnologias utilizadas

- Python
- Django
- SQLite
- HTML
- CSS
- Django Templates
- Django Crispy Forms
- Git
- GitHub

## Estrutura do projeto

```text
py-taxi-service-user-form-and-validation/
├── taxi/
│   ├── migrations/
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
├── taxi_service/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── templates/
├── static/
├── tests/
├── manage.py
├── requirements.txt
├── taxi_service_db_data.json
└── README.md
```

## Modelos principais

### Manufacturer

Representa uma fabricante de carros.

Principais campos:

- `name`: nome da fabricante;
- `country`: país de origem.

### Driver

Representa um motorista do serviço de táxi.

Principais campos:

- `username`: nome de usuário;
- `first_name`: primeiro nome;
- `last_name`: sobrenome;
- `license_number`: número da licença.

### Car

Representa um carro utilizado no serviço de táxi.

Principais campos:

- `model`: modelo do carro;
- `manufacturer`: fabricante do carro;
- `drivers`: motoristas associados ao carro.

## Validação da licença do motorista

O número da licença do motorista deve seguir um formato específico:

```text
AAA12345
```

Regras de validação:

- Deve conter exatamente 8 caracteres;
- Os 3 primeiros caracteres devem ser letras maiúsculas;
- Os 5 últimos caracteres devem ser números.

Exemplos:

```text
Válido: ABC12345
Inválido: abC12345
Inválido: ABC1234
Inválido: ABC12A45
```

## Associação entre motorista e carro

O projeto possui uma funcionalidade que permite ao usuário logado se associar a um carro.

Na página de detalhes do carro:

- Se o usuário ainda não estiver associado ao carro, será exibida uma opção para adicionar esse usuário ao carro;
- Se o usuário já estiver associado ao carro, será exibida uma opção para removê-lo.

Essa funcionalidade permite praticar relacionamentos muitos-para-muitos no Django.

## O que foi praticado

Este projeto permitiu praticar:

- Validação personalizada em formulários;
- Criação de usuários com campos adicionais;
- Atualização de campos específicos de um model;
- Relacionamentos muitos-para-muitos;
- Criação de ações personalizadas em views;
- Proteção de páginas com autenticação;
- Uso de Class-Based Views;
- Uso de checkboxes em formulários.

## Como executar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/WalterMatheusgg/py-taxi-service-user-form-and-validation.git
```

### 2. Acesse a pasta do projeto

```bash
cd py-taxi-service-user-form-and-validation
```

### 3. Crie um ambiente virtual

```bash
python -m venv venv
```

### 4. Ative o ambiente virtual

No Windows:

```bash
venv\Scripts\activate
```

No Linux/macOS:

```bash
source venv/bin/activate
```

### 5. Instale as dependências

```bash
pip install -r requirements.txt
```

### 6. Execute as migrações

```bash
python manage.py migrate
```

### 7. Carregue os dados iniciais

```bash
python manage.py loaddata taxi_service_db_data.json
```

### 8. Inicie o servidor

```bash
python manage.py runserver
```

Depois, acesse no navegador:

```text
http://127.0.0.1:8000/
```

## Usuário padrão

Após carregar os dados iniciais, é possível acessar com:

```text
Username: admin.user
Password: 1qazcde3
```

## Autor

Desenvolvido por **Walter Matheus** como parte da trilha de estudos em Django.
