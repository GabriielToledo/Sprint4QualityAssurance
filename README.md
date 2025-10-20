# Sprint4QualityAssurance
Link do azure devops com os testes: https://dev.azure.com/AssistenteVirtualXP/AssistienteVirtualXPI

Link para vídeo com casos de testes: https://youtu.be/IvoPA-NQ0p0

Integrantes:
- Gabriel Augusto Maciel Toledo - rm551654
- Gabriel Freitas - rm550187
- Guilherme Daher - rm98611
- Gustavo Akio - rm550241
- Heitor Nobre - rm551539

O Projeto

Estrutura de Testes no Azure Boards
Toda a gestão da qualidade do projeto foi centralizada no Azure Boards, onde os Casos de Teste foram definidos para cada Product Backlog Item (PBI) relevante. A principal diretriz em toda a definição de testes foi o uso rigoroso de Dados Controlados. Isso significa que, para cada teste, foram predefinidos os valores exatos de Input (dados de entrada) e os valores esperados de Output (dados de saída e Status Code).
A utilização de Dados Controlados garante que os testes sejam robustos e que a lógica de negócio, cálculo e segurança da API seja verificada com precisão.

Automação e Casos de Uso no Postman
Em conformidade com a Parte B dos requisitos, que exige a automação de testes para componentes de API sem interface de usuário, foi empregado o Postman como ferramenta principal. Esta abordagem resultou na criação de uma suíte de automação que cobre o mínimo de 4 casos de testes automatizados.

Os testes de caso de uso implementados no Postman visam validar a segurança e a funcionalidade básica do sistema:
- Cadastro de Usuário (Sucesso): Valida a criação de um novo registro, enviando um Input de email e senha e esperando o Output de um Status 201 Created e a confirmação de um novo id_usuario.
- Login com Senha Errada (Falha): Este é um caso de teste negativo crucial. Ele envia credenciais inválidas (senha incorreta) e espera o Output específico de segurança: Status 401 Unauthorized com a mensagem de erro "Senha errada".
- Fluxo de Verificação em Duas Etapas (Login que deu Certo): Este é um teste de fluxo complexo que valida o caso de uso de sucesso em duas etapas.

Passo 1 (Disparo): O envio de credenciais corretas deve gerar o Output Status 200 OK e o aviso de que o status é "2fa_pendente".

Passo 2 (Confirmação): O envio do código 2FA correto (que é um Input Controlado como "123456") valida o processo, resultando no Output final de Status 200 OK, mensagem de sucesso e o recebimento do token de sessão.
