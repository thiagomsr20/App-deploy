# Conceitos de DevOps na prática

Durante minha jornada com tecnologia, em muitos momentos me fiz a seguinte pergunta "Como isso sai da minha máquina e vai parar na do cliente tudo funcionando certinho? Sem eu precisar acessar o cliente e instalar manualmente".
Foi aí que acabei "esbarrando" em conceitos de configuração de pipeline, variados tipos de testes automatizados, esteira de deploy e conceito de entrega contínua (CI/CD)

A ideia desse projeto é elaborar um suplemento para SolidWorks com instalador e tudo, que consulte uma API que armazenará os dados do cliente e a última versão do projeto, dessa forma:

{
  "versao": "1.2.3",
  "url": "https://meuservidor.com/download/arquivosDaAplicao.zip",
  "updateMessage": "Correções de bugs"
}

A cada nova atualização na branch main do repositório, o GitHub Actions irá criptografar as DLL do projeto durante a compilação, disponibilizará a última versão dos arquivos DLL na API que armazenará as informações do cliente, e toda vez que a aplicação for iniciada no lado do cliente, ele fará uma consulta para essa API verificando se a versão do app no lado do cliente está condizente com a versão consultada no servidor.

Em caso de haver uma nova versão, pedir para o cliente se ele deseja atualizar a aplicação, em caso de positivo, ele irá instalar a nova versão na máquina do cliente.
