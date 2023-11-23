"# CUIDADO-SEGURO-MONITORANDO-O-BEM-ESTAR-" 

public class Main {
    public static void main(String[] args) {

        boolean Escola = true;
        boolean Horario7 = true;
        boolean Natacao = true;
        boolean Horario12 = true;
        boolean Curso = true;
        boolean Horario15 = true;
        boolean EstaNaEscola = Escola && Horario7;
        boolean EstaNaNatacao = Natacao && Horario12;
        boolean EstaNoCurso = Curso && Horario15;



        String escola = Escola ? "Esta Na Escola" : "Não Esta Na Escola";
        String natacao = Natacao ? "Esta Na Natação" : "Não Esta Na Natação";
        String curso = Curso ? "Esta No Curso" : "Não Esta No Curso";

        System.out.println(escola);
        System.out.println(natacao);
        System.out.println(curso);







    }

}

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class ConsultaBancoDados {

    public static void main(String[] args) {
        String url = "jdbc:mysql://seu_servidor:porta/seu_banco_de_dados";
        String usuario = "seu_usuario";
        String senha = "sua_senha";

        try (Connection conexao = DriverManager.getConnection(url, usuario, senha)) {

            // Consulta na tabela Pessoa
            String consultaPessoa = "SELECT * FROM Pessoa";
            try (PreparedStatement statementPessoa = conexao.prepareStatement(consultaPessoa);
                 ResultSet resultSetPessoa = statementPessoa.executeQuery()) {

                while (resultSetPessoa.next()) {
                    int id = resultSetPessoa.getInt("ID");
                    String nome = resultSetPessoa.getString("Nome");
                    String cpf = resultSetPessoa.getString("CPF");
                    String dataNascimento = resultSetPessoa.getString("DataNascimento");

                    // Faça algo com os dados, como imprimir na tela
                    System.out.println("ID: " + id + ", Nome: " + nome + ", CPF: " + cpf + ", Data Nascimento: " + dataNascimento);
                }
            }

            // Consulta na tabela Dependentes
            String consultaDependentes = "SELECT * FROM Dependentes";
            try (PreparedStatement statementDependentes = conexao.prepareStatement(consultaDependentes);
                 ResultSet resultSetDependentes = statementDependentes.executeQuery()) {

                while (resultSetDependentes.next()) {
                    int id = resultSetDependentes.getInt("ID");
                    int pessoaId = resultSetDependentes.getInt("PessoaID");
                    String nome = resultSetDependentes.getString("Nome");
                    String cpf = resultSetDependentes.getString("CPF");
                    String dataNascimento = resultSetDependentes.getString("DataNascimento");

                    // Faça algo com os dados, como imprimir na tela
                    System.out.println("ID: " + id + ", PessoaID: " + pessoaId + ", Nome: " + nome + ", CPF: " + cpf + ", Data Nascimento: " + dataNascimento);
                }
            }

        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
