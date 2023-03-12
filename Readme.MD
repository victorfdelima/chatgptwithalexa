# README - GPT-3 Powered Alexa Skill
Este é um exemplo de um Alexa Skill que utiliza a API do OpenAI GPT-3 para responder perguntas dos usuários. Quando o usuário faz uma pergunta, o Skill envia a pergunta para o GPT-3 para processamento e armazena a pergunta e a resposta em um bucket do Amazon S3.

##### Configuração
Antes de usar este Skill, você precisará configurar alguns serviços:

- Obtenha uma chave de API do OpenAI GPT-3 e substitua "YOUR_OPENAI_API_KEY" na linha 9 do código com a sua chave.

- Você pode pegar a sua API ou criar uma a partir desse link <https://platform.openai.com/account/api-keys>

- Crie um bucket do Amazon S3 e substitua "YOUR_S3_BUCKET_NAME" nas linhas 14 e 37 do código com o nome do seu bucket.

- O Skill usa o AWS SDK para Python (Boto3) para se conectar ao S3. Certifique-se de que suas credenciais do AWS estejam configuradas corretamente.

- Você precisará configurar e implantar este Skill como uma função Lambda do AWS. Consulte a documentação do AWS para obter mais informações sobre como fazer isso.

##### Funcionamento
O Skill tem dois handlers de request:

- GetGreetingHandler: quando o usuário diz "Alexa, abrir GPT-3 Skill", este handler é invocado. Ele retorna uma mensagem de boas-vindas.

- AskQuestionHandler: quando o usuário faz uma pergunta, este handler é invocado. Ele envia a pergunta para o GPT-3 para processamento e armazena a pergunta e a resposta no S3. Em seguida, ele retorna a resposta para o usuário.

- O Skill também tem um handler de exceção:

- CatchAllExceptionHandler: caso ocorra algum erro durante a execução do Skill, este handler é invocado. Ele retorna uma mensagem de erro genérica para o usuário.

##### Como Usar
Para usar este Skill, você precisará configurá-lo como uma Skill na Alexa Developer Console e implantá-lo como uma função Lambda no AWS.

Para configurar o Skill na Alexa Developer Console:

- Faça login na Alexa Developer Console.

- Crie uma nova Skill e configure as opções de nome, idioma e modelo de interação.

- Na seção "JSON Editor" do modelo de interação, cole o conteúdo do arquivo model.json.

- Crie uma função Lambda do AWS e implante o código do Skill na função.

- Copie o ARN da função Lambda e configure-o como o endpoint do Skill na seção "Endpoint" da Alexa Developer Console.

- Habilite o Skill e teste-o com a Alexa.

##### Limitações
Este é apenas um exemplo de como utilizar o OpenAI GPT-3 em um Alexa Skill. Tenha em mente que a API do GPT-3 é paga e pode ser limitada em termos de uso e acesso. Consulte a documentação do OpenAI para obter mais informações sobre as limitações e preços da API.

Além disso, este Skill é apenas um exemplo e não é destinado a ser usado em produção. É necessário fazer melhorias significativas no código para torná-lo robusto e escalável.