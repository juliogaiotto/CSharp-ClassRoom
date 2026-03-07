# Comandos C#
Trabalhar com C# no VS Code depende quase inteiramente da .NET CLI (Interface de Linha de Comando). Como o VS Code é um editor leve, esses comandos são essenciais para criar, compilar e rodar suas aplicações.

Aqui estão os comandos principais divididos por categoria:

---

## 1. Criação e Gerenciamento de Projetos
Esses comandos preparam o terreno para o seu código.

* Listar templates disponíveis:<br>
``dotnet new --list``

* Criar um novo projeto (Console, WebAPI, MVC, etc):<br>
``dotnet new console -n NomeDoProjeto``

* Criar um arquivo de Solução (.sln):<br>
``dotnet new sln -n NomeDaSolucao``

* Adicionar um projeto a uma solução:<br>
``dotnet sln add Caminho/Para/Projeto.csproj``

---
<br>

## 2. Desenvolvimento e Execução
O ciclo básico de "escrever, testar e rodar".

* Restaurar dependências (NuGet):<br>
``dotnet restore``

* Compilar o projeto:<br>
``dotnet build``

* Executar o projeto imediatamente:<br>
``dotnet run``

* Modo "Watch" (Reinicia o app automaticamente ao salvar alterações):<br>
``dotnet watch run``

    > __Dica:__ Esse é um dos mais úteis para produtividade no VS Code.

--- 

<br>

## 3. Gerenciamento de Pacotes (NuGet)
Para adicionar bibliotecas externas sem sair do terminal.

* Adicionar um pacote:<br>
``dotnet add package Newtonsoft.Json``

* Remover um pacote:<br>
``dotnet remove package Newtonsoft.Json``

* Adicionar referência de um projeto a outro:<br>
``dotnet add reference ../OutroProjeto/OutroProjeto.csproj``

---

<br>

## 4. Publicação e Limpeza
Para quando o código está pronto ou quando algo "estranho" acontece no build.

* Limpar artefatos de compilação (pastas bin e obj):
``dotnet clean``

* Publicar para produção (gera os arquivos finais):
``dotnet publish -c Release -o ./publish``

* Executar testes unitários:
``dotnet test``

|Objetivo|Comando|
|---|---|
|Criar Web API|``dotnet new webapi -n MinhaApi``|
|Rodar s/ Compilar|``dotnet run --no-build``|
|Ver Versão do SDK|``dotnet --version``|
|Ajuda Geral|``dotnet --help``|

>__Dica de Pro:__ No VS Code, você pode abrir o terminal integrado rapidamente com o atalho _Ctrl + `_

---

<br>

# Projetos

## 1. Projetos de Aplicativo (Executáveis) 
Estes são os pontos de partida mais comuns para aprender a linguagem ou construir serviços.

| Tipo de Projeto | Comando de Criação | Descrição |
| - | - | - |
|Console Application|``dotnet new console``|"O mais simples. Ideal para lógica pura, ferramentas de CLI e aprendizado."|
|Web API|``dotnet new webapi``|Cria um serviço RESTful com ASP.NET Core (usado em back-end).|
|Web App (Razor)|``dotnet new webapp``|Site com páginas que usam a sintaxe Razor do lado do servidor.|
|MVC|``dotnet new mvc``|Estrutura clássica Model-View-Controller para aplicações web.|
|Worker Service|``dotnet new worker``|Para processos que rodam em segundo plano (como serviços do Windows).|

## 2. Bibliotecas e Testes
Projetos que não rodam sozinhos, mas servem de apoio para outros.

|Tipo de Projeto|Comando de Criação|Descrição|
| - | - | - |
|Class Library|``dotnet new classlib``|Uma biblioteca reutilizável de classes (gera um arquivo .dll).|
|xUnit Test|``dotnet new xunit``|Projeto para criar testes unitários (padrão mais moderno).|
|MSTest|``dotnet new mstest``|Framework de testes nativo da Microsoft.|
|NUnit|``dotnet new nunit``|Outra alternativa popular para automação de testes.|

## 3. Interfaces de Usuário (Desktop/Mobile)
Para criar aplicações com janelas e elementos visuais.

* MAUI (Multi-platform App UI): Para apps Android, iOS, macOS e Windows.

``dotnet new maui``

* Blazor WebAssembly: Interface web que roda C# no navegador.

``dotnet new blazorwasm``

## 4. Parâmetros Essenciais na Criação
Ao rodar o comando de criação, você pode (e deve) usar alguns modificadores:

* Nomear o projeto: Por padrão, o .NET usa o nome da pasta. Para definir um nome específico:
``dotnet new console -n MeuProjetoIncrivel``

* Definir a pasta de saída: Para criar o projeto em uma pasta específica sem entrar nela primeiro:
``dotnet new console -o ./PastaDoProjeto``

* Desabilitar o HTTPS (em Web APIs): Útil para testes rápidos locais:
``dotnet new webapi --no-https``


>__Dica de Organização: O Arquivo de Solução (.sln)__
>
>Em projetos reais, é comum ter vários projetos (ex: uma API + uma Biblioteca + Testes). Para gerenciar todos juntos:
>
>1. Crie a solução: dotnet new sln -n MinhaSolucao
>
>2. Adicione os projetos a ela: dotnet sln add Caminho/Do/Projeto.csproj