Documentação dos Testes da API de Usuários

Objetivo
Esta documentação visa descrever a lógica e as decisões técnicas por trás dos testes automatizados para a API de Usuários do https://serverest.dev/ utilizando o Postman. O objetivo dos testes é verificar o comportamento da API nas operações CRUD (Create, Read, Update, Delete) para garantir que a API funcione conforme o esperado.

Lógica dos Testes
Cenário 1: Listar Usuários Cadastrados
  °Objetivo: Validar que a API retorna a lista de usuários cadastrados corretamente.
  °Lógica:
    .Verificação do Status Code: Assegura que o status da resposta seja 200, indicando sucesso.
    .Validação do Conteúdo da Resposta: Verifica se a resposta é um objeto e se contém uma quantidade de usuários superior a 0. Esta validação confirma que a API está retornando uma lista de usuários e que não está vazia.
    
Cenário 2: Cadastrar um Novo Usuário
  °Objetivo: Testar a criação de um novo usuário e garantir que o ID do novo usuário é retornado e armazenado para uso posterior.
  °Lógica:
    .Verificação do Status Code: Confirma que o status da resposta é 201, que indica que o recurso foi criado com sucesso.
    .Armazenamento do ID do Usuário: O ID do novo usuário é extraído da resposta e armazenado em uma variável de coleção (userId). Isso é crucial para os testes subsequentes que requerem o ID do usuário.
    .Validação da Presença do ID: Garante que o ID do usuário esteja presente na resposta, validando que a criação foi realizada corretamente.
    
Cenário 3: Buscar Usuário por ID
  °Objetivo: Verificar se a API retorna as informações corretas para um usuário específico, usando o ID obtido anteriormente.
  °Lógica:
    .Verificação do Status Code: Assegura que o status da resposta seja 200, indicando que a solicitação foi bem-sucedida.
    .Validação do Usuário: Compara o ID do usuário retornado com o ID armazenado na variável de coleção. Isso confirma que a API está retornando o usuário correto com base no ID fornecido.
    
Cenário 4: Editar Usuário
  °Objetivo: Testar a atualização dos dados de um usuário existente e verificar se a operação foi realizada com sucesso.
  °Lógica:
    .Verificação do Status Code: Confirma que o status da resposta é 200, indicando que a atualização foi bem-sucedida.
    .Validação da Mensagem de Sucesso: Verifica se a mensagem na resposta indica que o registro foi alterado com sucesso, garantindo que a atualização dos dados foi realizada corretamente.
    
Cenário 5: Excluir Usuário
  °Objetivo: Testar a exclusão de um usuário e confirmar que a operação foi concluída com sucesso.
  °Lógica:
    .Verificação do Status Code: Assegura que o status da resposta seja 200, indicando que a exclusão foi bem-sucedida.
    .Validação da Mensagem de Sucesso: Verifica se a mensagem na resposta confirma que o registro foi excluído com sucesso, garantindo que o usuário foi removido da base de dados.
    
Decisões Técnicas
1. Uso de Variáveis de Coleção: Utilizamos variáveis de coleção (userId) para armazenar o ID do usuário criado durante os testes. Isso permite que os testes subsequentes, como buscar, editar e excluir, usem o mesmo ID sem a necessidade de hardcoding, o que torna os testes mais flexíveis e reutilizáveis.

2. Validações de Status Code e Conteúdo: Cada teste verifica não apenas o status da resposta, mas também o conteúdo da resposta para garantir que a API está retornando os dados corretos e que as operações são realizadas conforme o esperado.

3. Estrutura de Testes: Os testes são estruturados para verificar aspectos específicos das operações CRUD, cobrindo tanto o comportamento da API quanto a integridade dos dados retornados.

4. Mensagens de Sucesso: A validação das mensagens de sucesso na resposta ajuda a garantir que a API está funcionando conforme o esperado e fornece feedback claro sobre o resultado das operações.

Conclusão
Esses testes ajudam a garantir que a API de Usuários está operando corretamente, validando não apenas o status das respostas, mas também o conteúdo e as mensagens de sucesso. Usar variáveis de coleção e validar o conteúdo da resposta permite uma abordagem mais robusta e flexível para testar a funcionalidade da API.

