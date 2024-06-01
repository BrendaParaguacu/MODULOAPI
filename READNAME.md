dotnet tool install --global dotnet-ef   

//adição de pacotes 
dotnet add package Microsoft.EntityFrameworkCore.Design   
dotnet add package Microsoft.EntityFrameworkCore.SqlServer

//criação de migrations
dotnet-ef migrations add CriacaoTabelaContato

//gera a tabela no banco de dados pq executa a migration
dotnet-ef database update

//se a classe não estiver no db set  como exemplo
public DbSet<Contato> Contatos { get; set; } 
//ele não vai criar a tabela

No nosso program.cs estamos usando o builder.services.addContext<agendaContext> passando o options que usamos no construtor la no agendaContext 

Quando usamos o UseSqlServer() para ele obter a conexão, usamos ele porque estamos usando um banco sql server, caso o banco seja outro, será usado outra função. 

E mandamos ele obter a connection string que demos o nome de <ConexaoPadrao>

