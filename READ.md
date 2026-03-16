# 🗺️ GeoPoints — Sistema de Gestão de Localizações

> Aplicação web para registo, visualização e pesquisa de localizações geográficas num mapa interativo, com sistema de autenticação e controlo de permissões por tipo de utilizador.

---

## 📋 Descrição do Projeto

O **GeoPoints** é uma aplicação web desenvolvida como projeto académico que permite gerir pontos de interesse no mapa (aeroportos, hospitais, museus, parques, entre outros). Os utilizadores podem inserir novas localizações através de um formulário ou clicando diretamente no mapa, pesquisar registos por país, cidade ou tipo, e gerir os seus próprios dados. Existe ainda um perfil de administrador com acesso total a todos os registos.

---

## ✅ Funcionalidades Implementadas

- **Sistema de Login** com dois tipos de utilizadores: Administrador e Utilizador Normal
- **Controlo de permissões:**
  - Administrador pode editar e apagar qualquer registo
  - Utilizador normal só pode editar e apagar os registos que ele próprio inseriu
- **Inserção de registos** através de formulário com os campos: nome, país, cidade, tipo, coordenadas e descrição
- **Inserção por clique no mapa** — ao clicar numa posição do mapa, as coordenadas são preenchidas automaticamente no formulário
- **Mapa interativo** (Leaflet.js) com marcadores personalizados por tipo de localização
- **Popups informativos** ao clicar nos marcadores com nome, tipo, cidade e descrição
- **Pesquisa/filtros** por País, Cidade e Tipo de localização
- **Lista lateral** de todos os registos com opções de edição e eliminação
- **Modal de edição rápida** diretamente a partir da lista
- **Interface responsiva** com tema visual laranja e preto

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Utilização |
|---|---|
| HTML5 / CSS3 / JavaScript | Frontend — estrutura, estilos e lógica |
| PHP 8+ | Backend — autenticação, CRUD e ligação à BD |
| MySQL / MariaDB | Base de dados relacional |
| [Leaflet.js](https://leafletjs.com/) v1.9.4 | Mapa interativo e marcadores |
| [CartoDB Dark Matter](https://carto.com/basemaps/) | Tiles do mapa (tema escuro) |
| phpMyAdmin | Gestão da base de dados |
| [Doxygen](https://www.doxygen.nl/) | Geração automática de documentação |

---

## 🚀 Instruções para Executar o Projeto Localmente

### Pré-requisitos

- [XAMPP](https://www.apachefriends.org/) (Apache + MySQL + PHP)
- Browser moderno (Chrome, Firefox, Edge)
- Ligação à internet (para o mapa e fontes)

---

### 1. Clonar o repositório

```bash
git clone https://github.com/teu-utilizador/geopoints.git
```

---

### 2. Colocar os ficheiros no servidor

Copia a pasta do projeto para o diretório `htdocs` do XAMPP:

```
C:\xampp\htdocs\geopoints\
```

---

### 3. Configurar a Base de Dados

1. Inicia o **XAMPP** e liga os serviços **Apache** e **MySQL**
2. Abre o **phpMyAdmin** em `http://localhost/phpmyadmin`
3. No separador **SQL**, cola o conteúdo de `passo1_criar_base_dados.sql` e clica **Executar**
4. Na lista da esquerda, clica em **geopoints** para a selecionar
5. No separador **SQL**, cola o conteúdo de `passo2_tabelas_e_dados.sql` e clica **Executar**

---

### 4. Configurar a ligação à base de dados

Edita o ficheiro `config/db.php` com as tuas credenciais:

```php
<?php
define('DB_HOST', 'localhost');
define('DB_NAME', 'geopoints');
define('DB_USER', 'root');      // utilizador do MySQL
define('DB_PASS', '');          // password do MySQL (vazia no XAMPP por defeito)
```

---

### 5. Abrir o site

Acede no browser a:

```
http://localhost/geopoints/
```

---

### 6. Credenciais de Acesso (Demo)

| Utilizador | Password | Tipo |
|---|---|---|
| `admin` | `admin123` | Administrador |
| `user1` | `user123` | Utilizador Normal |
| `user2` | `user456` | Utilizador Normal |
